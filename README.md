# Data Visualisation Matplotlib.pyplot

This is the overview of the `matplotlib` library in data visualization using python. This covers the basics of data visualization which is drawing some graphs, charts etc in python.

### Installation of packages

We are going to use:

- matplotlib.pyplot
- numpy

To install the required packages run the following command:

```shell
$pip install matplotlib
# Then
$pip install numpy

```

> Alternatively we can install the packages by running the following script

```
from pip._internal import main
packages = ['numpy', 'matplotlib']
for package in packages:
    main(['install', package])
```

Importing the packages
The following line of code import the packages that we are going to use.

```
import numpy as np
import matplotlib.pyplot as plt
# Reloading matplotlib to avoid some other errors
from importlib import reload
plt=reload(plt)
```

## 1. Line Graph

We are going to create a numpy array for our points.

> Example:

```
x1 = np.array([1, 2, 3, 4, 5])
y1 = x1.copy()*2

x2 = x1.copy()
y2 = x1.copy()**2
# plots for the first data
plt.plot(x1, y1, 'r-o', linewidth=2, markeredgecolor="blue", label="Boys")
# plots for the second data
#  from the third point it should be dashed
plt.plot(x2[:3], y2[:3], 'g--o', linewidth=2, markeredgecolor='red', label="Girls")
plt.plot(x2[2:], y2[2:], 'g--o', linewidth=2, markeredgecolor='red')

# Changing the x and y scales
plt.xticks([0, 1, 2, 3, 4, 5])
plt.yticks([0,4, 8, 12, 16, 20, 24, 28])

# Changing the labels the axis
plt.xlabel('x-axis')
plt.ylabel("x-axis")
# Plot Title
plt.title("Relationships", fontfamily="Arial", fontsize=20, fontweight='bold')
# Showing the key
plt.legend()
# Displaying the plot

plt.show()
```

> To Create a cool line graph visit the [Documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html)

## 2. Bar Graphs

#### Vertical Bars

`pyplot.bar(x, height, width=0.8, bottom=None, *, align='center', data=None, **kwargs)`

```
courses =np.array(["STA 111", "PAC 110", "CSC 113", "PHY 113", "PHY 114", "STA 121", "PAC 121", "CSC 121", "PHY 123", "PHY 124"])
marks =np.array([74, 89, 96, 93, 90, 79,90, 96, 93, 90])
barColors = np.array(["green", "orange", "lightseagreen", "purple", "red", "green", "orange", "lightseagreen", "purple", "red"])
plt.bar(courses, marks, width=.8, color=barColors)
plt.title("First Year Courses", fontsize=20, fontweight='bold', fontfamily ='Arial')

plt.xlabel("Courses", fontweight="bold", fontsize=18)
plt.ylabel("Marks (%)",  fontweight="bold", fontsize=18)
# changing the fisize
plt.rcParams["figure.figsize"] = (10, 5)

plt.show()
```

#### Horizontal Bars

`matplotlib.pyplot.barh(y, width, height=0.8, left=None, *, align='center', **kwargs)`

```
courses =np.array(["STA 111", "PAC 110", "CSC 113", "PHY 113", "PHY 114", "STA 121", "PAC 121", "CSC 121", "PHY 123", "PHY 124"])
marks =np.array([74, 89, 96, 93, 90, 79,90, 96, 93, 90])
barColors = np.array(["green", "orange", "lightseagreen", "purple", "red", "green", "orange", "lightseagreen", "purple", "red"])
plt.barh(courses, marks, color=barColors)
plt.title("First Year Courses", fontsize=20, fontweight='bold', fontfamily ='Arial')

plt.xlabel("Courses", fontweight="bold", fontsize=18)
plt.ylabel("Marks (%)",  fontweight="bold", fontsize=18)
# changing the fisize
plt.rcParams["figure.figsize"] = (10, 5)

plt.show()
```

## Documentation Reference

- [Documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html)
