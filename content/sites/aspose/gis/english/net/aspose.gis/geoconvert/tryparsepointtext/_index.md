---
title: GeoConvert.TryParsePointText
second_title: Aspose.GIS for .NET API Reference
description: GeoConvert method. Converts the string that contains сoordinates to IPoint object. A return value indicates whether the conversion succeeded or failed.
type: docs
weight: 30
url: /net/aspose.gis/geoconvert/tryparsepointtext/
---
## GeoConvert.TryParsePointText method

Converts the string that contains сoordinates to IPoint object. A return value indicates whether the conversion succeeded or failed.

```csharp
public static bool TryParsePointText(string text, out IPoint point)
```

| Parameter | Type | Description |
| --- | --- | --- |
| text | String | A string that contains coordinates to convert. The string should contain both coordinate latitude and longitude. Coordinates should be separated by whitespace, by comma or by semicolon. |
| point | IPoint& | When this method returns, contains the IPoint object with parsed coordinates, if the conversion succeeded, or null if the conversion failed. |

### Return Value

True if text was parsed successfully, otherwise False.

### Remarks

Examples: "80° 151°", "74°50.82', 172°08.21'", "80°;151°", "2CMB", "2CMB6682893142", "2C MB 66828 93142", "WMAQ12405535".

### See Also

* interface [IPoint](../../../aspose.gis.geometries/ipoint/)
* class [GeoConvert](../)
* namespace [Aspose.Gis](../../geoconvert/)
* assembly [Aspose.GIS](../../../)


