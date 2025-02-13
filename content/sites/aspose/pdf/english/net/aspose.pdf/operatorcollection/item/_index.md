---
title: Item
second_title: Aspose.PDF for .NET API Reference
description: Gets operator by its index.
type: docs
weight: 40
url: /net/aspose.pdf/operatorcollection/item/
---
## OperatorCollection indexer

Gets operator by its index.

```csharp
public override Operator this[int index] { get; set; }
```

| Parameter | Description |
| --- | --- |
| index | Index of operator. Numbering is starts from 1. |

### Return Value

Operator from requested index

### Examples

Example demonstrates how to get operator of page contents by index.

```csharp
Document doc = new Document("input.pdf");
OperatorCollection oc = doc.Pages[1].Contents;
Operator first = oc[1];
```

### See Also

* class [Operator](../../operator)
* class [OperatorCollection](../../operatorcollection)
* namespace [Aspose.Pdf](../../operatorcollection)
* assembly [Aspose.PDF](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.PDF.dll -->
