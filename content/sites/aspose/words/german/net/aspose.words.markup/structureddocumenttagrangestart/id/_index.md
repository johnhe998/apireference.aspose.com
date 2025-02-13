---
title: StructuredDocumentTagRangeStart.Id
second_title: Aspose.Words für .NET-API-Referenz
description: StructuredDocumentTagRangeStart eigendom. Gibt eine eindeutige schreibgeschützte persistente numerische ID für dieses strukturierte DokumentTag an.
type: docs
weight: 40
url: /de/net/aspose.words.markup/structureddocumenttagrangestart/id/
---
## StructuredDocumentTagRangeStart.Id property

Gibt eine eindeutige, schreibgeschützte, persistente numerische ID für dieses strukturierte Dokument-Tag an.

```csharp
public int Id { get; }
```

### Bemerkungen

Das ID-Attribut muss diesen Regeln folgen:

* Das Dokument soll die Tag-IDs des strukturierten Dokuments nur dann beibehalten, wenn das gesamte document geklont wird[`Clone`](../../../aspose.words/document/clone/).
* Während[`ImportNode`](../../../aspose.words/documentbase/importnode/) Die ID soll beibehalten werden, wenn der Import keine Konflikte mit anderen strukturierten Dokument-Tag-IDs im Zieldokument verursacht.
* Wenn mehrere strukturierte Dokument-Tag-Knoten denselben Dezimalzahlwert für das Id-Attribut angeben, dann soll das erste strukturierte Dokument-Tag im Dokument diese ursprüngliche ID beibehalten, und allen nachfolgenden strukturierten Dokument-Tag-Knoten werden neue Identifikatoren zugewiesen Das Dokument wird geladen.
* Während eines eigenständigen strukturierten Dokument-TagsINodeCloningListener) operation neue eindeutige ID wird für den geklonten strukturierten Dokument-Tag-Knoten be generiert.
* Wenn die ID im Quelldokument nicht angegeben ist, wird dem Tag-Knoten des strukturierten Dokuments eine neue eindeutige Kennung zugewiesen , wenn das Dokument geladen wird.

### Beispiele

Zeigt, wie die Eigenschaften von strukturierten Dokument-Tags mit mehreren Abschnitten abgerufen werden.

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

### Siehe auch

* class [StructuredDocumentTagRangeStart](../)
* namensraum [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* Montage [Aspose.Words](../../../)


