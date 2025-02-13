---
title: Document.PageCount
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Ruft die Anzahl der Seiten im Dokument ab wie durch die letzte Seitenlayoutoperation berechnet.
type: docs
weight: 300
url: /de/net/aspose.words/document/pagecount/
---
## Document.PageCount property

Ruft die Anzahl der Seiten im Dokument ab, wie durch die letzte Seitenlayoutoperation berechnet.

```csharp
public int PageCount { get; }
```

### Beispiele

Zeigt, wie die Anzahl der Seiten im Dokument gezählt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Page 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Page 3");

// Überprüfen Sie die erwartete Seitenzahl des Dokuments.
Assert.AreEqual(3, doc.PageCount);

// Das Abrufen der PageCount-Eigenschaft hat das Seitenlayout des Dokuments aufgerufen, um den Wert zu berechnen.
// Dieser Vorgang muss nicht wiederholt werden, wenn das Dokument in ein festes Seitenspeicherformat gerendert wird,
// wie .pdf. So können Sie gerade bei komplexeren Dokumenten etwas Zeit sparen.
doc.Save(ArtifactsDir + "Document.GetPageCount.pdf");
```

### Siehe auch

* method [UpdatePageLayout](../updatepagelayout/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


