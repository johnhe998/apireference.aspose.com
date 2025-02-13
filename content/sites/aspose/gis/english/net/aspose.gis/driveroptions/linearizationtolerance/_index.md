---
title: DriverOptions.LinearizationTolerance
second_title: Aspose.GIS for .NET API Reference
description: DriverOptions property. A tolerance to use to linearize curve geometries.
type: docs
weight: 50
url: /net/aspose.gis/driveroptions/linearizationtolerance/
---
## DriverOptions.LinearizationTolerance property

A tolerance to use to linearize curve geometries.

```csharp
public double LinearizationTolerance { get; set; }
```

### Property Value

The tolerance to pass to [`ToLinearGeometry`](../../../aspose.gis.geometries/geometry/tolineargeometry/) before adding geometries.

### Remarks

This is a creation options - it does not affect opening. If driver does not support non-linear geometries they are automatically linearized. This property specifies an argument to the [`ToLinearGeometry`](../../../aspose.gis.geometries/geometry/tolineargeometry/) method that is used for linearization.

### See Also

* class [DriverOptions](../)
* namespace [Aspose.Gis](../../driveroptions/)
* assembly [Aspose.GIS](../../../)


