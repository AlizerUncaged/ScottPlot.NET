---
Title: Marker - ScottPlot 4.1 Cookbook
Description: Plottable - Marker recipes
Source: https://github.com/ScottPlot/ScottPlot/tree/master/src/cookbook
---

## Marker

You can place individual markers anywhere on the plot. 

```cs
var plt = new ScottPlot.Plot(600, 400);

var colormap = ScottPlot.Drawing.Colormap.Turbo;
Random rand = new(0);
for (int i = 0; i < 100; i++)
{
    plt.AddMarker(
        x: rand.NextDouble(),
        y: rand.NextDouble(),
        size: 5 + rand.NextDouble() * 20,
        shape: Marker.Random(rand),
        color: colormap.RandomColor(rand));
}

plt.SaveFig("marker_quickstart.png");
```

<div class='text-center'>
<a href='../../images/marker_quickstart.png'><img src='../../images/marker_quickstart.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Draggable Marker

A special type of marker exists which allows dragging with the mouse.

```cs
var plt = new ScottPlot.Plot(600, 400);

plt.AddSignal(ScottPlot.DataGen.Sin(51));
plt.AddSignal(ScottPlot.DataGen.Cos(51));

var myDraggableMarker = new ScottPlot.Plottable.DraggableMarkerPlot()
{
    X = 25,
    Y = .57,
    Color = Color.Magenta,
    MarkerShape = MarkerShape.filledDiamond,
    MarkerSize = 15,
    Text = "drag the point!",
};

myDraggableMarker.TextFont.Size = 16;

plt.Add(myDraggableMarker);

plt.SaveFig("marker_draggable.png");
```

<div class='text-center'>
<a href='../../images/marker_draggable.png'><img src='../../images/marker_draggable.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Draggable Marker Snap

This is a type of marker which can be dragged with the mouse, but is restricted to to X/Y positions defined by two arrays.

```cs
var plt = new ScottPlot.Plot(600, 400);

// create random data and display it with a scatter plot
double[] xs = DataGen.Consecutive(50);
double[] ys = DataGen.Random(new Random(0), 50);
plt.AddScatter(xs, ys, label: "data");

// add a draggable marker that "snaps" to data values in that scatter plot
var dmpv = new ScottPlot.Plottable.DraggableMarkerPlotInVector()
{
    Xs = xs,
    Ys = ys,
    DragEnabled = true,
    IsVisible = true,
    MarkerSize = 15,
    MarkerShape = MarkerShape.filledDiamond,
    MarkerColor = Color.Magenta,
    Label = "marker",
};
plt.Add(dmpv);

plt.Legend();

plt.SaveFig("marker_draggableinvector.png");
```

<div class='text-center'>
<a href='../../images/marker_draggableinvector.png'><img src='../../images/marker_draggableinvector.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Labeled Marker

Markers have an optional text label.

```cs
var plt = new ScottPlot.Plot(600, 400);

plt.AddSignal(DataGen.Sin(51));

var marker = plt.AddMarker(35, 0.6);
marker.Text = "Interesting Point";
marker.TextFont.Color = Color.Magenta;
marker.TextFont.Alignment = Alignment.UpperCenter;
marker.TextFont.Size = 28;

plt.SaveFig("marker_labeled.png");
```

<div class='text-center'>
<a href='../../images/marker_labeled.png'><img src='../../images/marker_labeled.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Marker Line Width

Markers have options that can be customized, such as line width.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] ys1 = DataGen.Sin(30);
var cmap1 = ScottPlot.Drawing.Colormap.Viridis;

double[] ys2 = DataGen.Cos(30);
var cmap2 = ScottPlot.Drawing.Colormap.Turbo;

for (int i = 0; i < ys1.Length; i++)
{
    double frac = i / (ys1.Length - 1f);

    var circle = plt.AddMarker(i, ys1[i]);
    circle.MarkerShape = MarkerShape.openCircle;
    circle.MarkerSize = i + 5;
    circle.MarkerLineWidth = 1 + i / 2;
    circle.MarkerColor = cmap1.GetColor(1 - frac, .8);

    var triangle = plt.AddMarker(i, ys2[i]);
    triangle.MarkerShape = MarkerShape.openTriangleUp;
    triangle.MarkerSize = i + 5;
    triangle.MarkerLineWidth = 1 + i / 4;
    triangle.MarkerColor = cmap2.GetColor(frac, .8);
}

plt.Margins(.2, .2);

plt.SaveFig("marker_linewidth.png");
```

<div class='text-center'>
<a href='../../images/marker_linewidth.png'><img src='../../images/marker_linewidth.png' /></a>
</div>
