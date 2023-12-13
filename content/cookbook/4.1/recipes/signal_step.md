---
Title: "Step Display - ScottPlot 4.1 Cookbook"
Description: "Signal plots can be styled as step plots where points are connected by right angles instead of straight lines."
Date: 12/11/2023 8:13:10 PM
Version: ScottPlot 4.1.69
URL: /cookbook/4.1/recipes/signal_step/
BreadcrumbNames: ["ScottPlot 4.1 Cookbook", "Signal Plot", "Step Display"]
BreadcrumbUrls: ["/cookbook/4.1/", "/cookbook/4.1/category/plottable-signal-plot", "/cookbook/4.1/recipes/signal_step/"]
SearchUrl: "/cookbook/4.1/search/"
OgImage: "/cookbook/4.1/images/signal_step.png"
---

<h2><a id='step-display' href='/cookbook/4.1/recipes/signal_step/'>Step Display</a></h2>

Signal plots can be styled as step plots where points are connected by right angles instead of straight lines.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[] ys = DataGen.Sin(51);

var sig = plt.AddSignal(ys);
sig.StepDisplay = true;
sig.MarkerSize = 0;

plt.SaveFig("signal_step.png");
```

<img src='../../images/signal_step.png' class='d-block mx-auto my-5' />

