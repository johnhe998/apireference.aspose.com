---
title: MarkerCluster.FeaturesBasedConfiguration
second_title: Aspose.GIS for .NET API Reference
description: MarkerCluster property. A callback that is used to configure this symbolizer before rendering a cluster center.
type: docs
weight: 20
url: /net/aspose.gis.rendering.symbolizers/markercluster/featuresbasedconfiguration/
---
## MarkerCluster.FeaturesBasedConfiguration property

A callback that is used to configure this symbolizer before rendering a cluster center.

```csharp
public Action<IEnumerable<Feature>, MarkerCluster> FeaturesBasedConfiguration { get; set; }
```

### Remarks

This callback is invoked before rendering every cluster center. It accepts a features that are about to be rendered and a clone of this symbolizer. By changing properties of the clone, it is possible to update symbolizer's behavior based on features' attributes.

### See Also

* class [Feature](../../../aspose.gis/feature/)
* class [MarkerCluster](../)
* namespace [Aspose.Gis.Rendering.Symbolizers](../../markercluster/)
* assembly [Aspose.GIS](../../../)


