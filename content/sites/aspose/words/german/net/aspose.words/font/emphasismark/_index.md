---
title: Font.EmphasisMark
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Ruft das auf diese Formatierung angewendete Hervorhebungszeichen ab oder legt es fest.
type: docs
weight: 110
url: /de/net/aspose.words/font/emphasismark/
---
## Font.EmphasisMark property

Ruft das auf diese Formatierung angewendete Hervorhebungszeichen ab oder legt es fest.

```csharp
public EmphasisMark EmphasisMark { get; set; }
```

### Beispiele

Zeigt, wie zusätzliche Zeichen hinzugefügt werden, die über/unter dem Glyphenzeichen gerendert werden.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// Mögliche Arten von Hervorhebungen:
// https://apireference.aspose.com/words/net/aspose.words/emphasismark
builder.Font.EmphasisMark = emphasisMark; 

builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");

builder.Document.Save(ArtifactsDir + "Fonts.SetEmphasisMark.docx");
```

### Siehe auch

* enum [EmphasisMark](../../emphasismark/)
* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


