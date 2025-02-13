---
title: AbstractPath.Open
second_title: Aspose.GIS for .NET API Reference
description: AbstractPath method. Opens this AbstractPath as a file.
type: docs
weight: 120
url: /net/aspose.gis/abstractpath/open/
---
## AbstractPath.Open method

Opens this `AbstractPath` as a file.

```csharp
public abstract Stream Open(FileAccess access)
```

| Parameter | Type | Description |
| --- | --- | --- |
| access | FileAccess | Specifies a subset of operations that can be performed on a Stream. |

### Return Value

A Stream opened with the specified FileAccess.

### Remarks

If *access* has the flag Write set, and the file does not exist, an inheritor must create it.  An `AbstractPath` can be opened multiple times by `Aspose.GIS`. This is required in order to read a file independently with multiple streams. You should not cache the result but rather return new Stream every time this method is called.

### See Also

* class [AbstractPath](../)
* namespace [Aspose.Gis](../../abstractpath/)
* assembly [Aspose.GIS](../../../)


