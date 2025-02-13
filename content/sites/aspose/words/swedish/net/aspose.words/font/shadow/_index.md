---
title: Font.Shadow
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Sant om teckensnittet är formaterat som skuggat.
type: docs
weight: 330
url: /sv/net/aspose.words/font/shadow/
---
## Font.Shadow property

Sant om teckensnittet är formaterat som skuggat.

```csharp
public bool Shadow { get; set; }
```

### Exempel

Visar hur man skapar en serie text formaterad med en skugga.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ställ in Shadow-flaggan för att tillämpa en offset-skuggeffekt,
// får det att se ut som om bokstäverna svävar ovanför sidan.
builder.Font.Shadow = true;
builder.Font.Size = 36;

builder.Writeln("This text has a shadow.");

doc.Save(ArtifactsDir + "Font.Shadow.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


