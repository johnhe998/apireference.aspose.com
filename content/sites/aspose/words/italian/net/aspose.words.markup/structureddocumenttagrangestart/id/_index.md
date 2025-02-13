---
title: StructuredDocumentTagRangeStart.Id
second_title: Aspose.Words per .NET API Reference
description: StructuredDocumentTagRangeStart proprietà. Specifica un ID numerico persistente di sola lettura univoco per questo tag del documento strutturato.
type: docs
weight: 40
url: /it/net/aspose.words.markup/structureddocumenttagrangestart/id/
---
## StructuredDocumentTagRangeStart.Id property

Specifica un ID numerico persistente di sola lettura univoco per questo tag del documento strutturato.

```csharp
public int Id { get; }
```

### Osservazioni

L'attributo ID deve seguire queste regole:

* Il documento conserverà gli ID tag del documento strutturato solo se l'intero documento viene clonato[`Clone`](../../../aspose.words/document/clone/).
* In occasione[`ImportNode`](../../../aspose.words/documentbase/importnode/) L'ID deve essere mantenuto se l'importazione non causa conflitti con altri ID tag del documento strutturato in il documento di destinazione.
* Se più nodi di tag del documento strutturato specificano lo stesso valore numerico decimale per l'attributo Id, il primo tag del documento strutturato nel documento deve mantenere questo Id originale, e tutti i successivi nodi di tag del documento strutturato devono avere nuovi identificatori assegnati quando il documento è caricato.
* Durante tag documento strutturato autonomoINodeCloningListener) operazione nuovo ID univoco verrà generato per il nodo tag del documento strutturato clonato.
* Se Id non è specificato nel documento di origine, al nodo del tag del documento strutturato sarà assegnato un nuovo identificatore univoco quando il documento viene caricato.

### Esempi

Mostra come ottenere le proprietà dei tag di documenti strutturati a più sezioni.

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

### Guarda anche

* class [StructuredDocumentTagRangeStart](../)
* spazio dei nomi [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* assemblea [Aspose.Words](../../../)


