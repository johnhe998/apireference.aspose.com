---
title: FileGdbCoordinatePrecisionGrid.CreateFromRectangle
second_title: Aspose.GIS for .NET API Reference
description: FileGdbCoordinatePrecisionGrid method. Creates new FileGdbCoordinatePrecisionGrid such that all values within a rectangle are representable.
type: docs
weight: 20
url: /net/aspose.gis.formats.filegdb/filegdbcoordinateprecisiongrid/createfromrectangle/
---
## FileGdbCoordinatePrecisionGrid.CreateFromRectangle method

Creates new `FileGdbCoordinatePrecisionGrid` such that all values within a rectangle are representable.

```csharp
public static FileGdbCoordinatePrecisionGrid CreateFromRectangle(IPoint p1, IPoint p2)
```

| Parameter | Type | Description |
| --- | --- | --- |
| p1 | IPoint | One corner of the rectangle. |
| p2 | IPoint | Opposite corner of the rectangle. Must have same dimensions as *p1*. |

### Return Value

The `FileGdbCoordinatePrecisionGrid` such that all values within a rectangle are representable. Values outside of the rectangle are not representable, so all coordinates that will be written to FileGDB layer must be inside the rectangle.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |
| ArgumentException | *p1* and *p2* don't form a valid non empty rectangle: *p1* or *p2* is empty. 'HasZ' flags of *p1* does not equal to 'HasZ' flag of *p2*'HasM' flags of *p1* does not equal to 'HasM' flag of *p2*'X' coordinate of *p1* is equal to 'X' coordinate of *p2*'Y' coordinate of *p1* is equal to 'Y' coordinate of *p2*'Z' coordinate of *p1* is equal to 'Z' coordinate of *p2*'M' coordinate of *p1* is equal to 'M' coordinate of *p2* Any coordinate is NaN or infinity. |

### See Also

* interface [IPoint](../../../aspose.gis.geometries/ipoint/)
* class [FileGdbCoordinatePrecisionGrid](../)
* namespace [Aspose.Gis.Formats.FileGdb](../../filegdbcoordinateprecisiongrid/)
* assembly [Aspose.GIS](../../../)


