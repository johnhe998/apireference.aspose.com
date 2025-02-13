---
title: ParagraphFormat.Borders
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Paragrafın kenarlıklarının koleksiyonunu alır.
type: docs
weight: 50
url: /tr/net/aspose.words/paragraphformat/borders/
---
## ParagraphFormat.Borders property

Paragrafın kenarlıklarının koleksiyonunu alır.

```csharp
public BorderCollection Borders { get; }
```

### Örnekler

Üst kenarlıklı bir paragrafın nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### Ayrıca bakınız

* class [BorderCollection](../../bordercollection/)
* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


