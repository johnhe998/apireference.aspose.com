---
title: EsriAsciiDriver.OpenLayer
second_title: Aspose.GIS for .NET API Reference
description: EsriAsciiDriver method. Opens the layer for reading.
type: docs
weight: 20
url: /net/aspose.gis.formats.esriascii/esriasciidriver/openlayer/
---
## OpenLayer(AbstractPath, RasterDriverOptions) {#openlayer_2}

Opens the layer for reading.

```csharp
public override RasterLayer OpenLayer(AbstractPath path, RasterDriverOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| path | AbstractPath | Path to the file. |
| options | RasterDriverOptions | Driver-specific options. |

### Return Value

An instance of [`RasterLayer`](../../../aspose.gis.raster/rasterlayer/).

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentException | Options object has an incorrect type for this driver. |
| ArgumentNullException | The path is `null`. |
| IOException | An I/O error occurred. |
| NotSupportedException | Driver can not open raster layers (see [`CanOpenLayers`](../canopenlayers/)). |

### See Also

* class [RasterLayer](../../../aspose.gis.raster/rasterlayer/)
* class [AbstractPath](../../../aspose.gis/abstractpath/)
* class [RasterDriverOptions](../../../aspose.gis/rasterdriveroptions/)
* class [EsriAsciiDriver](../)
* namespace [Aspose.Gis.Formats.EsriAscii](../../esriasciidriver/)
* assembly [Aspose.GIS](../../../)

---

## OpenLayer(string, EsriAsciiOptions) {#openlayer_4}

Opens a layer for reading.

```csharp
public RasterLayer OpenLayer(string path, EsriAsciiOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| path | String | Path to the file. |
| options | EsriAsciiOptions | Driver-specific options. |

### Return Value

An instance of [`RasterLayer`](../../../aspose.gis.raster/rasterlayer/).

### See Also

* class [RasterLayer](../../../aspose.gis.raster/rasterlayer/)
* class [EsriAsciiOptions](../../esriasciioptions/)
* class [EsriAsciiDriver](../)
* namespace [Aspose.Gis.Formats.EsriAscii](../../esriasciidriver/)
* assembly [Aspose.GIS](../../../)

---

## OpenLayer(AbstractPath, EsriAsciiOptions) {#openlayer_1}

Opens a layer for reading.

```csharp
public RasterLayer OpenLayer(AbstractPath path, EsriAsciiOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| path | AbstractPath | Path to the file. |
| options | EsriAsciiOptions | Driver-specific options. |

### Return Value

An instance of [`RasterLayer`](../../../aspose.gis.raster/rasterlayer/).

### See Also

* class [RasterLayer](../../../aspose.gis.raster/rasterlayer/)
* class [AbstractPath](../../../aspose.gis/abstractpath/)
* class [EsriAsciiOptions](../../esriasciioptions/)
* class [EsriAsciiDriver](../)
* namespace [Aspose.Gis.Formats.EsriAscii](../../esriasciidriver/)
* assembly [Aspose.GIS](../../../)


