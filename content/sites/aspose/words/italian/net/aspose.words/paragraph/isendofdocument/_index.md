---
title: Paragraph.IsEndOfDocument
second_title: Aspose.Words per .NET API Reference
description: Paragraph proprietà. Vero se questo paragrafo è lultimo paragrafo nellultima sezione del documento.
type: docs
weight: 60
url: /it/net/aspose.words/paragraph/isendofdocument/
---
## Paragraph.IsEndOfDocument property

Vero se questo paragrafo è l'ultimo paragrafo nell'ultima sezione del documento.

```csharp
public bool IsEndOfDocument { get; }
```

### Esempi

Mostra come inserire un paragrafo nel documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;
paragraphFormat.KeepTogether = true;

// Il metodo "Writeln" termina il paragrafo dopo aver aggiunto il testo
// e quindi inizia una nuova riga, aggiungendo un nuovo paragrafo.
builder.Writeln("Hello world!");

Assert.True(builder.CurrentParagraph.IsEndOfDocument);
```

### Guarda anche

* class [Paragraph](../)
* spazio dei nomi [Aspose.Words](../../paragraph/)
* assemblea [Aspose.Words](../../../)


