# Superimposing Line Charts with Separate Axes

Wouldn't it be nice to have the number of themes and the number sets on the same chart? But what do we get if we just plot both of them the way we have before?

![[2020-10-10_10-09-52-88792d77cb4c28acc03af46a6b2d56ae.png|500]]

Well, that's not very informative! 🤦‍♀️ The problem is that the "number of themes" and the "number of sets" have very different scales. The theme number ranges between 0 and 90, while the number of sets ranges between 0 and 900. So what can we do?

## Two Separate Axes

We need to be able to configure and plot our data on two separate axes on the same chart. This involves getting hold of an axis object from Matplotlib.
```python
1. ax1 = plt.gca() # get current axes
2. ax2 = ax1.twinx() 
```

We then create another axis object: `ax2`. The key thing is that by using the `.twinx()` method allows `ax1` and `ax2` to share the same x-axis. When we plot our data on the axes objects we get this: