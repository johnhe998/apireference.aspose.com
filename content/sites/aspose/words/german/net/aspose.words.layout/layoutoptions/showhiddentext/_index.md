---
title: LayoutOptions.ShowHiddenText
second_title: Aspose.Words für .NET-API-Referenz
description: LayoutOptions eigendom. Ruft ab oder legt fest ob verborgener Text im Dokument gerendert wird. Standard ist False.
type: docs
weight: 70
url: /de/net/aspose.words.layout/layoutoptions/showhiddentext/
---
## LayoutOptions.ShowHiddenText property

Ruft ab oder legt fest, ob verborgener Text im Dokument gerendert wird. Standard ist False.

```csharp
public bool ShowHiddenText { get; set; }
```

### Bemerkungen

Diese Eigenschaft wirkt sich auf alle ausgeblendeten Inhalte aus, nicht nur auf Text.

### Beispiele

Zeigt, wie Text in einem gerenderten Ausgabedokument ausgeblendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Verborgenen Text einfügen, dann angeben, ob wir ihn aus einem gerenderten Dokument weglassen möchten.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

### Siehe auch

* class [LayoutOptions](../)
* namensraum [Aspose.Words.Layout](../../layoutoptions/)
* Montage [Aspose.Words](../../../)


