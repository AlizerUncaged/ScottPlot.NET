---
Title: Colorbar - ScottPlot 4.1 Cookbook
Description: Plottable - Colorbar recipes
Source: https://github.com/ScottPlot/ScottPlot/tree/master/src/cookbook
---

## Colorbar

A colorbar displays a colormap beside the data area. Colorbars are typically added to plots containing heatmaps.

```cs
var plt = new ScottPlot.Plot(600, 400);

plt.AddColorbar();

// direct attention to the colorbar
var text = plt.AddText("Colorbar", 5, 0, 24, Color.Red);
text.Alignment = Alignment.MiddleRight;
plt.AddArrow(7, 0, 5, 0, color: Color.Red);
plt.SetAxisLimits(-10, 10, -10, 10);

plt.SaveFig("colorbar_quickstart.png");
```

<div class='text-center'>
<a href='../../images/colorbar_quickstart.png'><img src='../../images/colorbar_quickstart.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Colorbar for Colormap

By default colorbars use the Viridis colormap, but this behavior can be customized and many colormaps are available.

```cs
var plt = new ScottPlot.Plot(600, 400);

plt.AddColorbar(Drawing.Colormap.Turbo);

// direct attention to the colorbar
var text = plt.AddText("Colorbar", 5, 0, 24, Color.Red);
text.Alignment = Alignment.MiddleRight;
plt.AddArrow(7, 0, 5, 0, color: Color.Red);
plt.SetAxisLimits(-10, 10, -10, 10);

plt.SaveFig("colorbar_colormap.png");
```

<div class='text-center'>
<a href='../../images/colorbar_colormap.png'><img src='../../images/colorbar_colormap.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Colorbar Ticks

Tick marks can be added to colorbars. Each tick is described by a position (a fraction of the distance from the bottom to the top) and a string (the tick label).

```cs
var plt = new ScottPlot.Plot(600, 400);

var cb = plt.AddColorbar(Drawing.Colormap.Turbo);

// Add manual ticks (disabling automatic ticks)
cb.AddTick(0, "-123");
cb.AddTick(1, "+123");
cb.AddTick(.5, "0");
cb.AddTick(.25, "-61.5");
cb.AddTick(.75, "+61.5");

// To re-enable automatic ticks call cb.AutomaticTicks(true)

// direct attention to the colorbar
var text = plt.AddText("Colorbar", 5, 0, 24, Color.Red);
text.Alignment = Alignment.MiddleRight;
plt.AddArrow(7, 0, 5, 0, color: Color.Red);
plt.SetAxisLimits(-10, 10, -10, 10);

plt.SaveFig("colorbar_ticks.png");
```

<div class='text-center'>
<a href='../../images/colorbar_ticks.png'><img src='../../images/colorbar_ticks.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Color Range

You can restrict a colorbar to only show a small range of a colormap. In this example we only use the middle of a rainbow colormap.

```cs
var plt = new ScottPlot.Plot(600, 400);

var cb = plt.AddColorbar(Drawing.Colormap.Turbo);
cb.MinValue = -10;
cb.MaxValue = 10;
cb.MinColor = .25;
cb.MaxColor = .75;

// direct attention to the colorbar
var text = plt.AddText("Colorbar", 5, 0, 24, Color.Red);
text.Alignment = Alignment.MiddleRight;
plt.AddArrow(7, 0, 5, 0, color: Color.Red);
plt.SetAxisLimits(-10, 10, -10, 10);

plt.SaveFig("colorbar_Range.png");
```

<div class='text-center'>
<a href='../../images/colorbar_range.png'><img src='../../images/colorbar_range.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Clipped value range

If data values extend beyond the min/max range displayed by a colorbar you can indicate the colormap is clipping the data values and inequality symbols will be displayed in the tick labeles at the edge of the colorbar.

```cs
var plt = new ScottPlot.Plot(600, 400);

var cb = plt.AddColorbar(Drawing.Colormap.Turbo);
cb.MinValue = -10;
cb.MaxValue = 10;
cb.MinIsClipped = true;
cb.MaxIsClipped = true;

// direct attention to the colorbar
var text = plt.AddText("Colorbar", 5, 0, 24, Color.Red);
text.Alignment = Alignment.MiddleRight;
plt.AddArrow(7, 0, 5, 0, color: Color.Red);
plt.SetAxisLimits(-10, 10, -10, 10);

plt.SaveFig("colorbar_clip.png");
```

<div class='text-center'>
<a href='../../images/colorbar_clip.png'><img src='../../images/colorbar_clip.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Scatter Plot with Colorbar

This example shows how to add differently colored markers to the plot to simulate a scatter plot with points colored according to a colorbar. Note that the colormap generates the colors, and that a colorbar just displays a colormap

```cs
var plt = new ScottPlot.Plot(600, 400);

var cmap = ScottPlot.Drawing.Colormap.Viridis;
plt.AddColorbar(cmap);

Random rand = new(0);
for (int i = 0; i < 1000; i++)
{
    double x = ScottPlot.DataGen.RandomNormalValue(rand, mean: 0, stdDev: .5);
    double y = ScottPlot.DataGen.RandomNormalValue(rand, mean: 0, stdDev: .5);
    double colorFraction = Math.Sqrt(x * x + y * y);
    System.Drawing.Color c = ScottPlot.Drawing.Colormap.Viridis.GetColor(colorFraction);
    plt.AddPoint(x, y, c);
}

plt.SaveFig("colorbar_scatter.png");
```

<div class='text-center'>
<a href='../../images/colorbar_scatter.png'><img src='../../images/colorbar_scatter.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Colorbar on Left

A colorbar may be added to the left side of the chart

```cs
var plt = new ScottPlot.Plot(600, 400);

plt.AddColorbar(rightSide: false);

plt.SaveFig("colorbar_left.png");
```

<div class='text-center'>
<a href='../../images/colorbar_left.png'><img src='../../images/colorbar_left.png' /></a>
</div>
