---
title: IStructuredDocumentTag Interface
linktitle: IStructuredDocumentTag
articleTitle: IStructuredDocumentTag
second_title: Aspose.Words for .NET
description: Aspose.Words.Markup.IStructuredDocumentTag interface. Interface to define a common data for StructuredDocumentTag and StructuredDocumentTagRangeStart in C#.
type: docs
weight: 3940
url: /net/aspose.words.markup/istructureddocumenttag/
---
## IStructuredDocumentTag interface

Interface to define a common data for [`StructuredDocumentTag`](../structureddocumenttag/) and [`StructuredDocumentTagRangeStart`](../structureddocumenttagrangestart/).

```csharp
public interface IStructuredDocumentTag
```

## Properties

| Name | Description |
| --- | --- |
| [Color](../../aspose.words.markup/istructureddocumenttag/color/) { get; set; } | Gets or sets the color of the structured document tag. |
| [Id](../../aspose.words.markup/istructureddocumenttag/id/) { get; } | Specifies a unique read-only persistent numerical Id for this **SDT**. |
| [IsShowingPlaceholderText](../../aspose.words.markup/istructureddocumenttag/isshowingplaceholdertext/) { get; set; } | Specifies whether the content of this **SDT** shall be interpreted to contain placeholder text (as opposed to regular text contents within the SDT). |
| [Level](../../aspose.words.markup/istructureddocumenttag/level/) { get; } | Gets the level at which this **SDT** occurs in the document tree. |
| [LockContentControl](../../aspose.words.markup/istructureddocumenttag/lockcontentcontrol/) { get; set; } | When set to true, this property will prohibit a user from deleting this **SDT**. |
| [LockContents](../../aspose.words.markup/istructureddocumenttag/lockcontents/) { get; set; } | When set to true, this property will prohibit a user from editing the contents of this **SDT**. |
| [Placeholder](../../aspose.words.markup/istructureddocumenttag/placeholder/) { get; } | Gets the [`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) containing placeholder text which should be displayed when this SDT run contents are empty, the associated mapped XML element is empty as specified via the [`XmlMapping`](./xmlmapping/) element or the [`IsShowingPlaceholderText`](./isshowingplaceholdertext/) element is true. |
| [PlaceholderName](../../aspose.words.markup/istructureddocumenttag/placeholdername/) { get; set; } | Gets or sets Name of the [`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) containing placeholder text. |
| [SdtType](../../aspose.words.markup/istructureddocumenttag/sdttype/) { get; } | Gets type of this **Structured document tag**. |
| [Tag](../../aspose.words.markup/istructureddocumenttag/tag/) { get; set; } | Specifies a tag associated with the current SDT node. Can not be null. |
| [Title](../../aspose.words.markup/istructureddocumenttag/title/) { get; set; } | Specifies the friendly name associated with this **SDT**. Can not be null. |
| [WordOpenXML](../../aspose.words.markup/istructureddocumenttag/wordopenxml/) { get; } | Gets a string that represents the XML contained within the node in the FlatOpc format. |
| [XmlMapping](../../aspose.words.markup/istructureddocumenttag/xmlmapping/) { get; } | Gets an object that represents the mapping of this structured document tag to XML data in a custom XML part of the current document. |

## Methods

| Name | Description |
| --- | --- |
| [IsRanged](../../aspose.words.markup/istructureddocumenttag/isranged/)() | Returns true if this instance is a ranged structured document tag. |
| [StructuredDocumentTagNode](../../aspose.words.markup/istructureddocumenttag/structureddocumenttagnode/)() | Returns Node object that implements this interface. |

### See Also

* namespace [Aspose.Words.Markup](../../aspose.words.markup/)
* assembly [Aspose.Words](../../)
