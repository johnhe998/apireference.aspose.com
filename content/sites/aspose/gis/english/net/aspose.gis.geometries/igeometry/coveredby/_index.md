---
title: IGeometry.CoveredBy
second_title: Aspose.GIS for .NET API Reference
description: IGeometry method. Determines whether this geometry is covered by a specified geometry.
type: docs
weight: 140
url: /net/aspose.gis.geometries/igeometry/coveredby/
---
## IGeometry.CoveredBy method

Determines whether this geometry is covered by a specified geometry.

```csharp
public bool CoveredBy(IGeometry other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| other | IGeometry | A geometry. |

### Return Value

`true` if this geometry is "spatially covered by" another geometry. `false` otherwise.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |
| ArgumentException | One of the geometries is invalid in such way that operation can not be finished. |
| ArgumentException | [`SpatialReferenceSystem`](../spatialreferencesystem/) of geometries are not equivalent. You can use [`SpatialReferenceSystemTransformation`](../../../aspose.gis.spatialreferencing/spatialreferencesystemtransformation/) in order to convert geometries to the same spatial reference system. |

### Remarks

This method tests whether one geometry is covered by another in terms of DE-9IM intersection matrix. This method is equivalent to:

```csharp
other.Covers(this);
```

### See Also

* method [SpatiallyContains](../spatiallycontains/)
* method [Covers](../covers/)
* interface [IGeometry](../)
* namespace [Aspose.Gis.Geometries](../../igeometry/)
* assembly [Aspose.GIS](../../../)


