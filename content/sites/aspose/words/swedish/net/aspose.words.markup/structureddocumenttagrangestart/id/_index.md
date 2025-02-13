---
title: StructuredDocumentTagRangeStart.Id
second_title: Aspose.Words för .NET API Referens
description: StructuredDocumentTagRangeStart fast egendom. Anger ett unikt skrivskyddat beständigt numeriskt ID för denna strukturerade dokumenttagg.
type: docs
weight: 40
url: /sv/net/aspose.words.markup/structureddocumenttagrangestart/id/
---
## StructuredDocumentTagRangeStart.Id property

Anger ett unikt skrivskyddat beständigt numeriskt ID för denna strukturerade dokumenttagg.

```csharp
public int Id { get; }
```

### Anmärkningar

Id-attribut ska följa dessa regler:

* Dokumentet ska behålla strukturerade dokumenttaggar-ID endast om hela document klonas[`Clone`](../../../aspose.words/document/clone/).
* Under[`ImportNode`](../../../aspose.words/documentbase/importnode/) Id ska behållas om importen inte orsakar konflikter med andra strukturerade dokumenttagg Id i måldokumentet.
* Om flera strukturerade dokumenttaggnoder anger samma decimaltalsvärde för Id-attributet, ska den första strukturerade dokumenttaggen i dokumentet behålla detta ursprungliga Id, och alla efterföljande strukturerade dokumenttaggnoder ska ha nya identifierare tilldelade när de dokumentet laddas.
* Under fristående strukturerad dokumenttaggINodeCloningListener) operation nytt unikt ID kommer att genereras för den klonade strukturerade dokumenttaggnoden.
* Om Id inte anges i källdokumentet, ska noden för strukturerade dokumenttagg ha en ny unik identifierare tilldelad när dokumentet laddas.

### Exempel

Visar hur du får egenskaperna för strukturerade dokumenttaggar med flera sektioner.

```csharp
Document doc = new Document(MyDir + "Multi-section structured document tags.docx");

StructuredDocumentTagRangeStart rangeStartTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true)[0] as StructuredDocumentTagRangeStart;
StructuredDocumentTagRangeEnd rangeEndTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeEnd, true)[0] as StructuredDocumentTagRangeEnd;

Console.WriteLine("StructuredDocumentTagRangeStart values:");
Console.WriteLine($"\t|Id: {rangeStartTag.Id}");
Console.WriteLine($"\t|Title: {rangeStartTag.Title}");
Console.WriteLine($"\t|PlaceholderName: {rangeStartTag.PlaceholderName}");
Console.WriteLine($"\t|IsShowingPlaceholderText: {rangeStartTag.IsShowingPlaceholderText}");
Console.WriteLine($"\t|LockContentControl: {rangeStartTag.LockContentControl}");
Console.WriteLine($"\t|LockContents: {rangeStartTag.LockContents}");
Console.WriteLine($"\t|Level: {rangeStartTag.Level}");
Console.WriteLine($"\t|NodeType: {rangeStartTag.NodeType}");
Console.WriteLine($"\t|RangeEnd: {rangeStartTag.RangeEnd}");
Console.WriteLine($"\t|Color: {rangeStartTag.Color.ToArgb()}");
Console.WriteLine($"\t|SdtType: {rangeStartTag.SdtType}");
Console.WriteLine($"\t|FlatOpcContent: {rangeStartTag.WordOpenXML}");
Console.WriteLine($"\t|Tag: {rangeStartTag.Tag}\n");

Console.WriteLine("StructuredDocumentTagRangeEnd values:");
Console.WriteLine($"\t|Id: {rangeEndTag.Id}");
Console.WriteLine($"\t|NodeType: {rangeEndTag.NodeType}");
```

### Se även

* class [StructuredDocumentTagRangeStart](../)
* namnutrymme [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* hopsättning [Aspose.Words](../../../)


