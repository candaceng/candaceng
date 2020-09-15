---
title: "Matplotlib - An Object Oriented Approach"
date: 2020-08-18
tags: [Python, Data Science]
excerpt: "Understanding the object oriented approach to Matplotlib"
---

In my [previous Matplotlib article]({% link _posts/2020-08-13-matplotlib.md %}), we've been using the *pyplot* object that we imported from the module. Notice that we did not have to create an instance of the object to use its methods.

### Figures and Axes
This is where figures and axes come in. A *figure* in Matplotlib refers to the window that contains our plots. The plots themselves are called *axes*. To generate multiple plots in a single figure, we can call `subplots()` to instantiate figures and axes objects. 
```python 
fig, ax = plt.subplots()
```
We now use our `ax` object to create plots instead of `plt`. Note below that when setting the x, y labels and the title, we need to prefix our original methods with `set_`. 
```python 
ax.plot(x, y)
ax.set_xlabel('x values')
ax.set_ylabel('y values')
ax.set_title('y vs. x')
```
By default we would only have a 1 by 1 `AxesSubplot` object since we called `plt.subplots()` without any parameters. If we wanted two plots side by side, we can call `plt.subplots(1, 2)`. This stores one list of two `AxesSubplot` objects into our `ax` variable (i.e. 1 row of 2 plots). If we wanted to store the plots individually instead of a list, we could instead initiate our variables using *unpacking*. 
``` python
fig, (ax1, ax2) = plt.subplots(1, 2) 
```
<br><img class="align-center" src="/images/matplotlib/fig-ax.PNG" style="border-radius: 5px; width: 50%;"><br>
We could also separate out the two by creating two figure objects instead of two axes objects.
```python
fig1, ax1 = plt.subplot()
fig2, ax2 = plt.subplot()
```
