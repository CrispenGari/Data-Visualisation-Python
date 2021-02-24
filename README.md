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

## 3. Pie charts

```
matplotlib.pyplot.pie(x, explode=None, labels=None, colors=None, autopct=None, pctdistance=0.6, shadow=False, labeldistance=1.1, startangle=0, radius=1, counterclock=True, wedgeprops=None, textprops=None, center=0, 0, frame=False, rotatelabels=False, *, normalize=None, data=None)
```

> Example:

```
## matplotlib.pyplot.pie(x, explode=None, labels=None, colors=None, autopct=None, pctdistance=0.6, shadow=False, labeldistance=1.1, startangle=0, radius=1, counterclock=True, wedgeprops=None, textprops=None, center=0, 0, frame=False, rotatelabels=False, *, normalize=None, data=None)

courses =np.array(["STA 111", "PAC 110", "CSC 113", "PHY 113", "PHY 114"])
marks =np.array([74, 89, 96, 93, 90])
colors = np.array(["green", "orange", "lightseagreen", "purple", "red"])

plt.title("First Year Courses", fontfamily="Arial", fontweight="bold", fontsize=20)
# plt.pie(marks, explode=True, labels=courses, colors=colors, shadow=True, counterclock=False, radius=2)
plt.pie(marks, explode=(0.1, 0, 0.1, 0, 0.1), labels=courses, colors=colors, shadow=True, counterclock=False, radius=1)
plt.legend()

plt.rcParams["figure.figsize"] = (8, 8)
plt.rcParams["figure.facecolor"] ='lightgray'
plt.show()
```

## 4. Box plots

```
matplotlib.pyplot.boxplot(x, notch=None, sym=None, vert=None, whis=None, positions=None, widths=None, patch_artist=None, bootstrap=None, usermedians=None, conf_intervals=None, meanline=None, showmeans=None, showcaps=None, showbox=None, showfliers=None, boxprops=None, labels=None, flierprops=None, medianprops=None, meanprops=None, capprops=None, whiskerprops=None, manage_ticks=True, autorange=False, zorder=None, *, data=None)
```

> Example

```


# matplotlib.pyplot.boxplot(x, notch=None, sym=None, vert=None, whis=None, positions=None, widths=None, patch_artist=None, bootstrap=None, usermedians=None, conf_intervals=None, meanline=None, showmeans=None, showcaps=None, showbox=None, showfliers=None, boxprops=None, labels=None, flierprops=None, medianprops=None, meanprops=None, capprops=None, whiskerprops=None, manage_ticks=True, autorange=False, zorder=None, *, data=None)
marks =np.array([74, 89, 96, 93, 90])

plt.boxplot(marks, flierprops=dict(markerfacecolor='r', marker='D'))

plt.show()

```

## 5. Histogram

```
matplotlib.pyplot.hist(x, bins=None, range=None, density=False, weights=None, cumulative=False, bottom=None, histtype='bar', align='mid', orientation='vertical', rwidth=None, log=False, color=None, label=None, stacked=False, *, data=None, **kwargs)
```

> Example

```
# matplotlib.pyplot.hist(x, bins=None, range=None, density=False, weights=None, cumulative=False, bottom=None, histtype='bar', align='mid', orientation='vertical', rwidth=None, log=False, color=None, label=None, stacked=False, *, data=None, **kwargs)

marks =np.array([10, 18, 55, 78, 45, 99, 100, 0])
plt.hist(marks, cumulative=True, bins=10)
plt.show()
```

## 6. Scatter plot

```
matplotlib.pyplot.scatter(x, y, s=None, c=None, marker=None, cmap=None, norm=None, vmin=None, vmax=None, alpha=None, linewidths=None, verts=<deprecated parameter>, edgecolors=None, *, plotnonfinite=False, data=None, **kwargs)[source]
```

> Example

```
# matplotlib.pyplot.scatter(x, y, s=None, c=None, marker=None, cmap=None, norm=None, vmin=None, vmax=None, alpha=None, linewidths=None, verts=<deprecated parameter>, edgecolors=None, *, plotnonfinite=False, data=None, **kwargs)

x = np.random.randint(5, 100, 10)
y = np.random.randint(0, 200, 10)

plt.scatter(x, y)
plt.title("Scatter Plot", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.xlabel("x-axis", fontweight="bold", fontsize=15)
plt.ylabel("y-axis", fontweight="bold", fontsize=15)
plt.show()
```

> Example: Drawing a scatter plot with a regression line

```
from numpy.polynomial.polynomial import polyfit
x = np.random.randint(5, 100, 10)
y = np.random.randint(0, 200, 10)

constant, gradient = polyfit(x, y, 1)

plt.plot(x, gradient*x + constant, '-r', linewidth=1)
plt.scatter(x, y)
plt.title("Scatter Plot", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.xlabel("x-axis", fontweight="bold", fontsize=15)
plt.ylabel("y-axis", fontweight="bold", fontsize=15)
plt.show()
```

## 7. Adding Text to the plot

```
matplotlib.pyplot.text(x, y, s, fontdict=None, **kwargs)
```

> Example:

```
plt.rcParams["figure.figsize"] = (5, 2)
plt.rcParams["figure.facecolor"] ='green'
plt.title("Writting Text", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.text(0.2, 0.4, s="MATPLOTLIB", color="red", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.show()
```

## 8. Saving figs

```
savefig(fname, dpi=None, facecolor='w', edgecolor='w',
        orientation='portrait', papertype=None, format=None,
        transparent=False, bbox_inches=None, pad_inches=0.1,
        frameon=None, metadata=None)
```

> Example: We want to save our previous plot

```
# matplotlib.pyplot.text(x, y, s, fontdict=None, **kwargs)

plt.rcParams["figure.figsize"] = (5, 2)
plt.rcParams["figure.facecolor"] ='green'
plt.title("Writting Text", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.text(0.2, 0.4, s="MATPLOTLIB", color="red", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.show()
plt.savefig("matplotlib.png")
```

### There are a lot of things to cover in matplotlib.pyplot such as

- hsv
- table
- subplot
- etc
  - Refer to the [documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.) for more

# READING IMAGES, SHOWING IMAGES AND SAVING IMAGES

## 1. imread()

    * `matplotlib.pyplot.imread(fname, format=None)`
    * Read an image from a file into an array.

> Example: we want to read an image with name `avatar.jpg` from our file and display it as array.

    ```
    image = plt.imread('avatar.jpg')
    image
    ```

## 2. imshow()

- Display data as an image, i.e., on a 2D regular raster.
  `matplotlib.pyplot.imshow(X, cmap=None, norm=None, aspect=None, interpolation=None, alpha=None, vmin=None, vmax=None, origin=None, extent=None, *, filternorm=True, filterrad=4.0, resample=None, url=None, data=None, **kwargs)[source]`
  > Example 1: We want to display `avatar.jpg` on the plot
- Read the image into an array
- Show the image PIL array in the plot

```
image = plt.imread('avatar.jpg')
plt.imshow(image)
plt.title("Displaying An Image", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.rcParams["figure.figsize"] = (5,5)
plt.rcParams["figure.facecolor"] ='white'
plt.show()
```

> Example 2: Creating a black image with the same dimensions as avatar.jpg and display it on the screen.

```
blackImage = np.zeros_like(image)
plt.imshow(blackImage)
plt.title("Displaying A Black Image", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.show()
```

> Example 3: Changing the black image to white image

```
blackImage = np.zeros_like(image)

whiteImage = np.full_like(blackImage, [255,255,255])
plt.imshow(whiteImage)
plt.title("White Image", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.show()
```

## 3. imsave()

- We want to create a green image with the same dimensions with our previous white image and save it as `green.jpg`.
- matplotlib.pyplot.imsave(fname, arr, \*\*kwargs)
  > Example:

```
blackImage = np.zeros_like(image)

whiteImage = np.full_like(blackImage, [255,255,255])
greenImage = np.full_like(whiteImage, [0, 255, 0])
plt.imshow(greenImage)
# Saving the image
plt.imsave('green.jpg', greenImage)
print("THE IMAGE HAS BEEN SAVED")
plt.title("White Image", fontfamily="Arial", fontweight="bold", fontsize=20)
plt.show()
```

> For more information Read The documentation

## Documentation Reference

- [Documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html)
- [Plots Markers](https://matplotlib.org/stable/api/markers_api.html)
