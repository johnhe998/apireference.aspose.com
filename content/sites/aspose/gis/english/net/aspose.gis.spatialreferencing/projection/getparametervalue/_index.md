---
title: Projection.GetParameterValue
second_title: Aspose.GIS for .NET API Reference
description: Projection method. Gets parameter with specified name of this projection.
type: docs
weight: 40
url: /net/aspose.gis.spatialreferencing/projection/getparametervalue/
---
## Projection.GetParameterValue method

Gets parameter with specified name of this projection.

```csharp
public double GetParameterValue(string name, ParameterType type = ParameterType.Other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| name | String | Name of parameter. |
| type | ParameterType | Type of parameter. Defines unit factor that will be deapplied: if type is Linear then [`LinearParametersUnit`](../linearparametersunit/) will be deapplied and result will be in meters. if type is Angular then [`AngularParametersUnit`](../angularparametersunit/) will be deapplied and result will be in radians. if type is Other parameter value will be returned 'as is'. |

### Return Value

Parameter with specified name.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is null. |
| InvalidOperationException | There is no parameter with this name. |

### See Also

* enum [ParameterType](../../parametertype/)
* class [Projection](../)
* namespace [Aspose.Gis.SpatialReferencing](../../projection/)
* assembly [Aspose.GIS](../../../)


