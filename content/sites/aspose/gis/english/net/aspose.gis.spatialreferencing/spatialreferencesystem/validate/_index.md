---
title: SpatialReferenceSystem.Validate
second_title: Aspose.GIS for .NET API Reference
description: SpatialReferenceSystem method. Determine if this SRS is valid.
type: docs
weight: 240
url: /net/aspose.gis.spatialreferencing/spatialreferencesystem/validate/
---
## SpatialReferenceSystem.Validate method

Determine if this SRS is valid.

```csharp
public abstract bool Validate(out string errorMessage)
```

| Parameter | Type | Description |
| --- | --- | --- |
| errorMessage | String& | If method return `false`, then this is description of invalidity. |

### Return Value

`true` if SRS is valid, `false` otherwise.

### Remarks

Valid SRS must have valid ellipsoid. - Geographic SRS must have exactly one East/West axis, exactly one North/South axis, and optional Up/Down axis (optional axis is present when geographic SRS is a compound of 2D geographic SRS and vertical SRS). - Projected SRS must have exactly one East/West axis, exactly one North/South axis, and optional Up/Down axis (optional axis is present when projected SRS is a compound of 2D geographic SRS and vertical SRS). - Geocentric SRS must have exactly one East/West axis, exactly one North/South axis and exactly one Other axis. - Vertical SRS must have exactly one Up/Down axis. - Local SRS must have at least one axis. Axises directions doesn't meter. - Compound SRS must be a combination of a valid Geographic/Projected and a valid Vertical SRS.

### See Also

* class [SpatialReferenceSystem](../)
* namespace [Aspose.Gis.SpatialReferencing](../../spatialreferencesystem/)
* assembly [Aspose.GIS](../../../)


