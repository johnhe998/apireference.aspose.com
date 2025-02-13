---
title: Font.TintAndShade
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Ruft einen DoubleWert ab oder legt ihn fest der eine Farbe aufhellt oder abdunkelt.
type: docs
weight: 520
url: /de/net/aspose.words/font/tintandshade/
---
## Font.TintAndShade property

Ruft einen Double-Wert ab oder legt ihn fest, der eine Farbe aufhellt oder abdunkelt.

```csharp
public double TintAndShade { get; set; }
```

### Bemerkungen

Die zulässigen Werte für diese Eigenschaft liegen im Bereich von -1 (am dunkelsten) bis 1 (am hellsten). Null (0) ist neutral. Der Versuch, diese Eigenschaft auf einen Wert kleiner als -1 oder größer als 1 festzulegen, führt zu aArgumentOutOfRangeException.

Das Festlegen dieser Eigenschaft für ein Font-Objekt mit Nicht-Thema colors führt zu aInvalidOperationException.

### Beispiele

Zeigt, wie Themenstile erstellt und verwendet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Erstellen Sie einen Stil mit Schriftarteigenschaften des Themas.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


