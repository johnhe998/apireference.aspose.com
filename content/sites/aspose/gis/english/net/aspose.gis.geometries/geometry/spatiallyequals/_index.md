---
title: Geometry.SpatiallyEquals
second_title: Aspose.GIS for .NET API Reference
description: Geometry method. Determines if this geometry spatially equal to a specified geometry.
type: docs
weight: 370
url: /net/aspose.gis.geometries/geometry/spatiallyequals/
---
## Geometry.SpatiallyEquals method

Determines if this geometry spatially equal to a specified geometry.

```csharp
public bool SpatiallyEquals(IGeometry other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| other | IGeometry | A geometry. |

### Return Value

`true` if this geometry "spatially equals" to specified geometry. `false` otherwise.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |
| ArgumentException | One of the geometries is invalid in such way that operation can not be finished. |
| ArgumentException | [`SpatialReferenceSystem`](../../igeometry/spatialreferencesystem/) of geometries are not equivalent. You can use [`SpatialReferenceSystemTransformation`](../../../aspose.gis.spatialreferencing/spatialreferencesystemtransformation/) in order to convert geometries to the same spatial reference system. |

### Remarks

This method tests equality in terms of DE-9IM intersection matrix. It does not depend on order of components (e.g. order of interior rings in polygon), Z and M values. Basically, it tests that two geometries occupy the same "space" when projected on two dimensional space. This method is equivalent to:

```csharp
this.Relate(other, "T*F**FFF*");
```

See OpenGIS Simple Features Specification for more details about DE-9IM.

### See Also

* interface [IGeometry](../../igeometry/)
* class [Geometry](../)
* namespace [Aspose.Gis.Geometries](../../geometry/)
* assembly [Aspose.GIS](../../../)


