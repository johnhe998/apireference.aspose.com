---
title: ParagraphFormat.OutlineLevel
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Belgedeki paragrafın anahat düzeyini belirtir.
type: docs
weight: 240
url: /tr/net/aspose.words/paragraphformat/outlinelevel/
---
## ParagraphFormat.OutlineLevel property

Belgedeki paragrafın anahat düzeyini belirtir.

```csharp
public OutlineLevel OutlineLevel { get; set; }
```

### Örnekler

Daraltılabilir metin oluşturmak için paragraf anahat düzeylerinin nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Her paragrafın 1'den 9'a kadar herhangi bir sayı veya varsayılan "BodyText" değerinde olabilen bir Anahat Düzeyi vardır.
// Özelliği numaralı değerlerden birine ayarlamak, solda bir ok gösterecektir.
// paragrafın başında.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.Level1;
builder.Writeln("Paragraph outline level 1.");

// Seviye 1 en üst seviyedir. Daha yüksek düzeyde bir paragrafın altında daha düşük düzeyde bir paragraf varsa,
// üst düzey paragrafın daraltılması, alt düzey paragrafın daraltılmasına neden olur.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.Level2;
builder.Writeln("Paragraph outline level 2.");

// Aynı seviyedeki iki paragraf birbirini daraltmaz,
// ve oklar işaret ettikleri paragrafları daraltmaz.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.Level3;
builder.Writeln("Paragraph outline level 3.");
builder.Writeln("Paragraph outline level 3.");

// Varsayılan "BodyText" değeri, herhangi bir düzeydeki bir paragrafın daraltılabileceği en düşük değerdir.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.BodyText;
builder.Writeln("Paragraph at main text level.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphOutlineLevel.docx");
```

### Ayrıca bakınız

* enum [OutlineLevel](../../outlinelevel/)
* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


