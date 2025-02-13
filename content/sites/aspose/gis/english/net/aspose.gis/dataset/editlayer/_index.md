---
title: Dataset.EditLayer
second_title: Aspose.GIS for .NET API Reference
description: Dataset method. Opens the layer with specified name for editing.
type: docs
weight: 90
url: /net/aspose.gis/dataset/editlayer/
---
## Dataset.EditLayer method

Opens the layer with specified name for editing.

```csharp
public abstract VectorLayer EditLayer(string name, DriverOptions options = null, 
    SpatialReferenceSystem spatialReferenceSystem = null)
```

| Parameter | Type | Description |
| --- | --- | --- |
| name | String | Name of the layer to edit. |
| options | DriverOptions | Open options. |
| spatialReferenceSystem | SpatialReferenceSystem | Spatial reference system for new geometries. |

### Return Value

The layer opened for editing.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentException | Layer with specified name does not exist; Options object has an incorrect type for this dataset. |
| ArgumentException | Options object has an incorrect type for this dataset. |
| ArgumentNullException | The name is `null`. |
| [GisException](../../gisexception/) | Error reading the feature from the layer. |
| IOException | An I/O error occurred. |

### See Also

* class [VectorLayer](../../vectorlayer/)
* class [DriverOptions](../../driveroptions/)
* class [SpatialReferenceSystem](../../../aspose.gis.spatialreferencing/spatialreferencesystem/)
* class [Dataset](../)
* namespace [Aspose.Gis](../../dataset/)
* assembly [Aspose.GIS](../../../)


