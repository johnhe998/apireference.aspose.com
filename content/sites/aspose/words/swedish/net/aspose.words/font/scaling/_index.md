---
title: Font.Scaling
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Hämtar eller ställer in teckenbreddsskalning i procent.
type: docs
weight: 310
url: /sv/net/aspose.words/font/scaling/
---
## Font.Scaling property

Hämtar eller ställer in teckenbreddsskalning i procent.

```csharp
public int Scaling { get; set; }
```

### Exempel

Visar hur man ställer in horisontell skalning och avstånd för tecken.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Lägg till en serie text och öka teckenbredden till 150 %.
builder.Font.Scaling = 150;
builder.Writeln("Wide characters");

// Lägg till en serie text och lägg till 1 pkt extra horisontellt mellanrum mellan varje tecken.
builder.Font.Spacing = 1;
builder.Writeln("Expanded by 1pt");

// Lägg till en rad text och för tecknen närmare varandra med 1 pkt.
builder.Font.Spacing = -1;
builder.Writeln("Condensed by 1pt");

doc.Save(ArtifactsDir + "Font.ScalingSpacing.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


