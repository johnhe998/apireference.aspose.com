---
title: Document.ViewOptions
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Bietet Optionen zum Steuern der Anzeige des Dokuments in Microsoft Word.
type: docs
weight: 450
url: /de/net/aspose.words/document/viewoptions/
---
## Document.ViewOptions property

Bietet Optionen zum Steuern der Anzeige des Dokuments in Microsoft Word.

```csharp
public ViewOptions ViewOptions { get; }
```

### Beispiele

Zeigt, wie Sie einen benutzerdefinierten Zoomfaktor festlegen, der ältere Versionen von Microsoft Word beim Laden auf ein Dokument anwenden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

Zeigt, wie Sie einen benutzerdefinierten Zoomtyp festlegen, der ältere Versionen von Microsoft Word beim Laden auf ein Dokument anwenden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Legen Sie die Eigenschaft "ZoomType" auf "ZoomType.PageWidth" fest, um Microsoft Word zu erhalten
// um das Dokument automatisch an die Breite der Seite anzupassen.
// Legen Sie die Eigenschaft "ZoomType" auf "ZoomType.FullPage" fest, um Microsoft Word zu erhalten
// um das Dokument automatisch zu zoomen, um die gesamte erste Seite sichtbar zu machen.
// Setzen Sie die Eigenschaft "ZoomType" auf "ZoomType.TextFit", um Microsoft Word zu erhalten
// um das Dokument automatisch zu zoomen, um es an die inneren Textränder der ersten Seite anzupassen.
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### Siehe auch

* class [ViewOptions](../../../aspose.words.settings/viewoptions/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


