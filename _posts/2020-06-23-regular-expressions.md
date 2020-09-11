---
title: "An Introduction to Regular Expressions"
date: 2020-06-23
tags: [python, tutorial, regular expressions]
excerpt: "Finding patterns in text to extract useful information"
---

### Background
During my summer 2020 internship, I implemented Python scripts that would pull specific information from a structured PDF. This process mainly consisted of finding patterns in the text to figure out where information such as dates or prices could be found. You can check out more details about this project [here]({% link _portfolio/pdf-parsing.md %}). 

### Python Regular Expressions
This is where the *re* module comes in. It's a standard library in Python that leverages the concept of regular expressions and can directly be imported. 
```python
import re
```
*Patterns* are denoted by specific characters, and you'll likely need to refer [documentation](https://docs.python.org/3/library/re.html), where you'll find a full list of what each character represents. For now, we'll start simple with the basics. Let's say we want to search for the word "test". Then our pattern would be "test" and a *re.Match* object would be returned if we compared it against "testing" or "detest". The span tells us the index position of the match. 
```python
re.search('test', 'testing') 
# <re.Match object; span=(0, 4), match='test'>
re.search('test', 'detest')  
# <re.Match object; span=(2, 6), match='test'>
```
What if we just wanted to match any word in general? That's where the backslash comes in. In Python 3, '\w' matches the first instance of a single word character. This includes unicode characters, ideograms, digits, or underscores. The opposite pattern is '\W' and it matches anything that is *not* a word character. 

It is likely that you wouldn't want to match just a single character, so we can use quantifiers to specify how many characters we want to match. 
<table style="margin-left:auto; margin-right:auto;">
    <tr><th>Pattern</th><th>&emsp; Match</th></tr>
    <tr><td>\w{2}</td><td>&emsp; 2 characters</td></tr>
    <tr><td>\w{2, 3}</td><td>&emsp; 2-3 characters</td></tr>
    <tr><td>\w{2,}</td><td>&emsp; 2 or more characters</td></tr>
    <tr><td>\w*</td><td>&emsp; 0 or more characters</td></tr>
    <tr><td>\w+</td><td>&emsp; 1 or more characters</td></tr>
</table><br>
If we wanted to match digits specifically we can use '\d'. Thus a pattern like '\w+\d{2}' would match any string with 1 or more word characters followed by 2 digits. Similar to the case with word characters, the pattern '\D' denotes any character that is *not* a digit. 

```python
re.search('\w+\d{2}', 'testingtesting123') 
# <re.Match object; span=(0, 17), match='testingtesting123'>
```
We also have specific syntax for representing whitespace characters, denoted by '\s'. So if I tried to match the above pattern with the string "testing testing 123" instead, there would be no match.  

With our new knowledge, matching a date becomes trivial. 
```python
re.search('\d{2}-\d{2}-\d{4}', 'matching a date: 04-23-2020')  
# <re.Match object; span=(17, 27), match='04-23-2020'>
```

### Metacharacters
Extending the example above, what if our we wanted to detect dates that use another separator besides a dash, such as '04/23/2020'? We could use the metacharacter '.' which represents any character that is not a newline. 
```python
re.search('\d{2}.\d{2}.\d{4}', 'matching a date: 04-23-2020')
# <re.Match object; span=(17, 27), match='04-23-2020'>
re.search('\d{2}.\d{2}.\d{4}', 'matching a date: 04/23/2020')
# <re.Match object; span=(17, 27), match='04/23/2020'>
```
But here's the problem: a string like '01234556789' would also qualify as a match because the metacharacter '.' also picks up on digits. If we wanted only to allow the '-' and '/' separators, we could instead use square brackets to specify exactly which characters we want matched. 
```python 
re.search('\d{2}[-/]\d{2}[-/]\d{4}', 'matching a date: 04-23-2020')
```
Some other useful metacharacters can be used to search for sentences that start with or end with a certain pattern. The metacharacters '^' and '$' do just that. 
```python
re.search('^test', 'testing')
# <re.Match object; span=(0, 4), match='test'>
re.search('test$', 'detest')
# <re.Match object; span=(2, 6), match='test'>
```
What if we wanted to find a match with a literal character, such as the dollar sign in a price? We would need to escape it with a backslash before the dollar sign, since '$' is a metacharacter. Note that '.' is also a metacharacter, but since its special meaning is "any character that is not a newline", we can still generate a match without escaping it. 
```python
re.search('\$\d{2}.\d{2}', 'matching a price: $10.23')
# <re.Match object; span=(18, 24), match='$10.23'>
```

### Summary
This article only covered the basics of regular expressions to give you an idea of how they can be used to extract information from something like a text file. A lot more functionality (e.g. iterating over all matches, grouping, using logic operators) can be found in the [documentation](https://docs.python.org/3/library/re.html).


