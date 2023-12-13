---
Title: "Show Levels - ScottPlot 4.1 Cookbook"
Description: "The value of each gauge is displayed as text by default but this behavior can be overridden. Note that this is different than the labels fiels which is what appears in the legened."
Date: 12/11/2023 8:13:10 PM
Version: ScottPlot 4.1.69
URL: /cookbook/4.1/recipes/radialgauge_levels/
BreadcrumbNames: ["ScottPlot 4.1 Cookbook", "Radial Gauge", "Show Levels"]
BreadcrumbUrls: ["/cookbook/4.1/", "/cookbook/4.1/category/plottable-radialgauge", "/cookbook/4.1/recipes/radialgauge_levels/"]
SearchUrl: "/cookbook/4.1/search/"
OgImage: "/cookbook/4.1/images/radialgauge_levels.png"
---

<h2><a id='show-levels' href='/cookbook/4.1/recipes/radialgauge_levels/'>Show Levels</a></h2>

The value of each gauge is displayed as text by default but this behavior can be overridden. Note that this is different than the labels fiels which is what appears in the legened.

```cs
var plt = new ScottPlot.Plot(600, 400);

plt.Palette = ScottPlot.Palette.Nord;
double[] values = { 100, 80, 65, 45, 20 };

var gauges = plt.AddRadialGauge(values);
gauges.ShowLevels = false;

plt.SaveFig("radialgauge_levels.png");
```

<img src='../../images/radialgauge_levels.png' class='d-block mx-auto my-5' />

