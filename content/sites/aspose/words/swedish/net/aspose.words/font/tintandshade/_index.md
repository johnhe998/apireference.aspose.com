---
title: Font.TintAndShade
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Hämtar eller ställer in ett dubbelt värde som gör en färg ljusare eller mörkare.
type: docs
weight: 520
url: /sv/net/aspose.words/font/tintandshade/
---
## Font.TintAndShade property

Hämtar eller ställer in ett dubbelt värde som gör en färg ljusare eller mörkare.

```csharp
public double TintAndShade { get; set; }
```

### Anmärkningar

De tillåtna värdena ligger inom området -1 (mörkast) till 1 (ljusast) för den här egenskapen. Noll (0) är neutral. Ett försök att ställa in den här egenskapen till ett värde mindre än -1 eller mer än 1 resulterar i enArgumentOutOfRangeException.

Att ställa in den här egenskapen för Font-objekt med icke-tema colors resulterar i enInvalidOperationException.

### Exempel

Visar hur man skapar och använder stil med teman.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Skapa lite stil med egenskaper för tematypsnitt.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


