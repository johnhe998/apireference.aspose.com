---
title: Font.BoldBi
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Sant om texten från höger till vänster är formaterad som fetstil.
type: docs
weight: 50
url: /sv/net/aspose.words/font/boldbi/
---
## Font.BoldBi property

Sant om texten från höger till vänster är formaterad som fetstil.

```csharp
public bool BoldBi { get; set; }
```

### Exempel

Visar hur man definierar separata uppsättningar teckensnittsinställningar för text från höger till vänster och höger till vänster.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definiera en uppsättning teckensnittsinställningar för text från vänster till höger.
builder.Font.Name = "Courier New";
builder.Font.Size = 16;
builder.Font.Italic = false;
builder.Font.Bold = false;
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// Definiera ytterligare en uppsättning teckensnittsinställningar för text från höger till vänster.
builder.Font.NameBi = "Andalus";
builder.Font.SizeBi = 24;
builder.Font.ItalicBi = true;
builder.Font.BoldBi = true;
builder.Font.LocaleIdBi = new CultureInfo("ar-AR", false).LCID;

// Vi kan använda Bidi-flaggan för att indikera om texten vi ska lägga till
// med dokumentbyggaren är från höger till vänster. När vi lägger till text med denna flagga inställd på sant,
// det kommer att formateras med hjälp av teckensnittsinställningarna från höger till vänster.
builder.Font.Bidi = true;
builder.Write("مرحبًا");

// Ställ in flaggan på false och lägg sedan till vänster till höger text.
// Dokumentbyggaren formaterar dessa med hjälp av teckensnittsinställningarna från vänster till höger.
builder.Font.Bidi = false;
builder.Write(" Hello world!");

doc.Save(ArtifactsDir + "Font.Bidi.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


