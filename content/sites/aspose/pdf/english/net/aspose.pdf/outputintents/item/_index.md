---
title: Item
second_title: Aspose.PDF for .NET API Reference
description: Gets the output intent at the specified index.
type: docs
weight: 30
url: /net/aspose.pdf/outputintents/item/
---
## OutputIntents indexer

Gets the output intent at the specified *index*.

```csharp
public OutputIntent this[int index] { get; }
```

| Parameter | Description |
| --- | --- |
| index | The zero-based index of the output intent to get. |

### Return Value

The output intent at the specified *index*.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentOutOfRangeException | *index* is less than 0 or *index* is equal to or greater than [`Count`](../count). |
| InvalidOperationException | The document that contains the collection has no catalog to access the OutputIntents. |

### See Also

* class [OutputIntent](../../outputintent)
* class [OutputIntents](../../outputintents)
* namespace [Aspose.Pdf](../../outputintents)
* assembly [Aspose.PDF](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.PDF.dll -->
