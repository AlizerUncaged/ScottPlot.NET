---
Title: Text Formatting - ScottPlot 5.0 Cookbook
Description: Text formatting can be extensively customized.
URL: /cookbook/5.0/Text/Formatting
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Text", "Text Formatting"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Text", "/cookbook/5.0/Text/Formatting"]
Date: 12/13/2023 2:24:04 PM
Version: ScottPlot 5.0.10-beta
---

# Text Formatting



<div class='alert alert-warning' role='alert'><h4 class='alert-heading py-0 my-0'>⚠️ ScottPlot 5.0.10-beta is a preview package</h4><hr /><p class='mb-0'><span class='fw-semibold'>This page describes a beta release of ScottPlot.</span> It is available on NuGet as a preview package, but its API is not stable and it is not recommended for production use. See the <a href='https://scottplot.net/versions/'>ScottPlot Versions</a> page for more information. </p></div>



Text formatting can be extensively customized.

[![](/cookbook/5.0/images/Formatting.png)](/cookbook/5.0/images/Formatting.png)

```cs
ScottPlot.Plot myPlot = new();

var text = myPlot.Add.Text("Hello, World", 42, 69);
text.Label.FontSize = 26;
text.Label.Bold = true;
text.Label.Rotation = -45;
text.Label.ForeColor = Colors.Yellow;
text.Label.BackColor = Colors.Navy.WithAlpha(.5);
text.Label.BorderColor = Colors.Magenta;
text.Label.BorderWidth = 3;
text.Label.Padding = 10;
text.Label.Alignment = Alignment.MiddleCenter;

myPlot.SavePng("demo.png");

```
