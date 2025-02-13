---
title: DocumentBuilder.Underline
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder eigendom. Ermittelt/legt den Unterstreichungstyp für die aktuelle Schriftart fest.
type: docs
weight: 170
url: /de/net/aspose.words/documentbuilder/underline/
---
## DocumentBuilder.Underline property

Ermittelt/legt den Unterstreichungstyp für die aktuelle Schriftart fest.

```csharp
public Underline Underline { get; set; }
```

### Beispiele

Zeigt, wie von einem Document Builder eingefügter Text formatiert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Underline = Underline.Dash;
builder.Font.Color = Color.Blue;
builder.Font.Size = 32;

// Der Builder wendet die Formatierung auf seinen aktuellen Absatz und jeden neu hinzugefügten Text danach an.
builder.Writeln("Large, blue, and underlined text.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertUnderline.docx");
```

### Siehe auch

* enum [Underline](../../underline/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


