---
Title: Signal Marker Size - ScottPlot 5.0 Cookbook
Description: Signal plots can have markers displayed at each point which are only visible when the plot is zoomed in.
URL: /cookbook/5.0/Signal/SignalMarkerSize/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Signal Plot", "Signal Marker Size"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Signal", "/cookbook/5.0/Signal/SignalMarkerSize"]
Date: 2024-01-10
Version: ScottPlot 5.0.13-beta
Version: ScottPlot 5.0.13-beta
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---

# Signal Marker Size



<div class='alert alert-warning' role='alert'><h4 class='alert-heading py-0 my-0'>⚠️ ScottPlot 5.0.13-beta is a preview package</h4><hr /><p class='mb-0'><span class='fw-semibold'>This page describes a beta release of ScottPlot.</span> It is available on NuGet as a preview package, but its API is not stable and it is not recommended for production use. See the <a href='https://scottplot.net/versions/'>ScottPlot Versions</a> page for more information. </p></div>



Signal plots can have markers displayed at each point which are only visible when the plot is zoomed in.

[![](/cookbook/5.0/images/SignalMarkerSize.png)](/cookbook/5.0/images/SignalMarkerSize.png)

```cs
ScottPlot.Version.ShouldBe(5, 0, 13);
ScottPlot.Plot myPlot = new();

var sig1 = myPlot.Add.Signal(Generate.Cos());
sig1.Label = "Default";
sig1.Data.YOffset = 3;

var sig2 = myPlot.Add.Signal(Generate.Cos());
sig2.Label = "Large Markers";
sig2.MaximumMarkerSize = 20;
sig2.Data.YOffset = 2;

var sig3 = myPlot.Add.Signal(Generate.Cos());
sig3.Label = "Hidden Markers";
sig3.MaximumMarkerSize = 0;
sig3.Data.YOffset = 1;

myPlot.Legend.IsVisible = true;

myPlot.SavePng("demo.png");

```

<a href='https://github.com/ScottPlot/ScottPlot/blob/main/src/ScottPlot5/ScottPlot5%20Cookbook/Recipes/PlotTypes/Signal.cs'><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="mb-1 bi bi-github" viewBox="0 0 16 16">
  <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
</svg> Edit on GitHub</a>
