---
title: ParagraphFormat.AddSpaceBetweenFarEastAndDigit
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Ruft ein Flag ab oder setzt es das angibt ob der Abstand zwischen den Zeichen automatisch zwischen den Regionen von Zahlen und den Regionen von ostasiatischem Text im aktuellen Absatz angepasst wird.
type: docs
weight: 20
url: /de/net/aspose.words/paragraphformat/addspacebetweenfareastanddigit/
---
## ParagraphFormat.AddSpaceBetweenFarEastAndDigit property

Ruft ein Flag ab oder setzt es, das angibt, ob der Abstand zwischen den Zeichen automatisch zwischen den Regionen von Zahlen und den Regionen von ostasiatischem Text im aktuellen Absatz angepasst wird.

```csharp
public bool AddSpaceBetweenFarEastAndDigit { get; set; }
```

### Beispiele

Zeigt, wie Sie einen Absatz in das Dokument einfügen.

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

// Die Methode "Writeln" beendet den Absatz nach dem Anhängen von Text
// und beginnt dann eine neue Zeile und fügt einen neuen Absatz hinzu.
builder.Writeln("Hello world!");

Assert.True(builder.CurrentParagraph.IsEndOfDocument);
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


