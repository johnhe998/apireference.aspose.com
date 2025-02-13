---
title: GeoGenerator.ProduceLines
second_title: Aspose.GIS for .NET API Reference
description: GeoGenerator method. Creates a new ILineString Enumerator with a given number of random items all of them within a given extent.
type: docs
weight: 10
url: /net/aspose.gis.geotools/geogenerator/producelines/
---
## GeoGenerator.ProduceLines method

Creates a new ILineString Enumerator with a given number of random items, all of them within a given extent.

```csharp
public static IEnumerable<ILineString> ProduceLines(Extent rect, LineGeneratorOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| rect | Extent | Specified area (see [`Extent`](../../../aspose.gis/extent/)) |
| options | LineGeneratorOptions | Line creation options (see [`LineGeneratorOptions`](../../linegeneratoroptions/)) |

### Return Value

Array of lines (see enumeration of [`ILineString`](../../../aspose.gis.geometries/ilinestring/))

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentOutOfRangeException | Number of lines must be grater then one. |
| NullReferenceException | Extent must have a value (not be NULL) |

### See Also

* interface [ILineString](../../../aspose.gis.geometries/ilinestring/)
* class [Extent](../../../aspose.gis/extent/)
* class [LineGeneratorOptions](../../linegeneratoroptions/)
* class [GeoGenerator](../)
* namespace [Aspose.Gis.GeoTools](../../geogenerator/)
* assembly [Aspose.GIS](../../../)


