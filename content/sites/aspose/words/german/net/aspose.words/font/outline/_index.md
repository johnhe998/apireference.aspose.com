---
title: Font.Outline
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Wahr wenn die Schriftart als Kontur formatiert ist.
type: docs
weight: 290
url: /de/net/aspose.words/font/outline/
---
## Font.Outline property

Wahr, wenn die Schriftart als Kontur formatiert ist.

```csharp
public bool Outline { get; set; }
```

### Beispiele

Zeigt, wie Sie einen als Gliederung formatierten Textverlauf erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Setzen Sie das Outline-Flag, um die Füllfarbe des Textes in Weiß zu ändern und
 // Lassen Sie einen dünnen Umriss um jedes Zeichen in der Originalfarbe des Textes.
builder.Font.Outline = true;
builder.Font.Color = Color.Blue;
builder.Font.Size = 36;

builder.Writeln("This text has an outline.");

doc.Save(ArtifactsDir + "Font.Outline.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


