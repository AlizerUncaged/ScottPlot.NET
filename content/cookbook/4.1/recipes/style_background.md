---
Title: "Background Color - ScottPlot 4.1 Cookbook"
Description: "Plots have two background colors that can be individually customized. The figure background is the background of the whole image. The data background is the background of the rectangle that contains the data. Both background types support transparency, although PNG file export is required."
Date: 12/11/2023 8:13:09 PM
Version: ScottPlot 4.1.69
URL: /cookbook/4.1/recipes/style_background/
BreadcrumbNames: ["ScottPlot 4.1 Cookbook", "Style", "Background Color"]
BreadcrumbUrls: ["/cookbook/4.1/", "/cookbook/4.1/category/style", "/cookbook/4.1/recipes/style_background/"]
SearchUrl: "/cookbook/4.1/search/"
OgImage: "/cookbook/4.1/images/style_background.png"
---

<h2><a id='background-color' href='/cookbook/4.1/recipes/style_background/'>Background Color</a></h2>

Plots have two background colors that can be individually customized. The figure background is the background of the whole image. The data background is the background of the rectangle that contains the data. Both background types support transparency, although PNG file export is required.

```cs
var plt = new ScottPlot.Plot(600, 400);

plt.AddSignal(DataGen.Sin(51));
plt.AddSignal(DataGen.Cos(51));

plt.Style(
    figureBackground: Color.LightSkyBlue,
    dataBackground: Color.Salmon);

plt.SaveFig("style_background.png");
```

<img src='../../images/style_background.png' class='d-block mx-auto my-5' />

