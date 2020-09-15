---
title: "Basic Matplotlib Concepts"
date: 2020-08-13
tags: [Python, Data Science]
excerpt: "A popular tool for data visualization in Python"
---

Matplotlib is a popular Python library used to create beautiful visualizations. It helps to provide a quick summary of data, and is often used in data science when performing an exploratory data analysis. 

### Getting Started 
If you don't have Matplotlib already, you can install it with a quick `pip install matplotlib` and then import it into our program. *Pyplot* is Matplotlib's plotting framework and it is common to simplify the name to *plt*.
```python
from matplotlib import pyplot as plt
```
Let's start with a simple line plot. We only need a list of x values and a list of y values to pass to the `plot` function on the *plt* module.  
```python
x = [1, 2, 3]
y = [1, 2, 3]
plt.plot(x, y)
plt.show()
```
<img class="align-center" src="/images/matplotlib/simple-line.PNG" style="border-radius: 5px; width: 50%;"><br>

The *plt* module also provides methods for adding a title and axes labels.
```python
plt.xlabel('x values')
plt.ylabel('y values')
plt.title('y vs. x')
```
Additional parameters of the `plot` function (such as `color`, `linestyle`, and `label`) can also be added to enhance our plot. A full list of parameters and styles can be found in the [documentation](https://matplotlib.org/3.3.1/api/_as_gen/matplotlib.pyplot.plot.html). We can also plot multiple lines before calling `plt.show()`.
```python
plt.plot(x, y, color='blue', linestyle='dashed', label='line 1')
y2 = [3, 2, 1]
plt.plot(x, y2, color='red', linestyle='solid', label='line 2')
```
<img class="align-center" src="/images/matplotlib/multiple-lines.PNG" style="border-radius: 5px; width: 50%;"><br>

Besides the basic line plots, the *plt* module also has specific methods for creating bar charts, pie charts, scatter plots, and histograms. Each type of plot also comes with certain parameters that you can find in the [pyplot documentation](https://matplotlib.org/api/pyplot_api.html). 
```python
plt.bar(<parameters>)
plt.pie(<parameters>)
plt.scatter(<parameters>)
plt.hist(<parameters>)
```

The *plt* module also comes with a list of styles and you can experiment with them to find one you like. You can check out all the available styles with the command below.
```python
plt.style.available
['Solarize_Light2', '_classic_test_patch', 'bmh', 'classic', 
'dark_background', 'fast', 'fivethirtyeight' 'ggplot', 'grayscale', 
'seaborn', 'seaborn-bright', 'seaborn-colorblind', 'seaborn-dark', 
'seaborn-dark-palette', 'seaborn-darkgrid', 'seaborn-deep', 
'seaborn-muted', 'seaborn-notebook', 'seaborn-paper', 'seaborn-pastel', 
'seaborn-poster', 'seaborn-talk', 'seaborn-ticks', 'seaborn-white', 
'seaborn-whitegrid', 'tableau-colorblind10']
```

To save an image to your local machine, you can simply run the `savefig` method.
```python
plt.savefig('myfig.png')
```

If you want to produce a multiple plots at a time, you will need to take the object oriented approach to Matplotlib, which is discussed [here]({% link _posts/2020-08-18-oop-matplotlib.md %})
