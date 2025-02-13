---
title: AbstractPath.GetFileName
second_title: Aspose.GIS for .NET API Reference
description: AbstractPath method. Returns the file name and extension of this AbstractPath.
type: docs
weight: 80
url: /net/aspose.gis/abstractpath/getfilename/
---
## AbstractPath.GetFileName method

Returns the file name and extension of this [`AbstractPath`](../).

```csharp
public string GetFileName()
```

### Return Value

The characters after the last [`Separator`](../separator/) character in the [`Location`](../location/). If the last character is the [`Separator`](../separator/) character, an empty string is returned. If there is no [`Separator`](../separator/) characters in the [`Location`](../location/), the [`Location`](../location/) itself is returned.

### Examples

For an `AbstractPath` with [`Location`](../location/) equal to `"/directory/file.txt"` and [`Separator`](../separator/) equal to `'/'`, this method returns `"file.txt"`.

### See Also

* class [AbstractPath](../)
* namespace [Aspose.Gis](../../abstractpath/)
* assembly [Aspose.GIS](../../../)


