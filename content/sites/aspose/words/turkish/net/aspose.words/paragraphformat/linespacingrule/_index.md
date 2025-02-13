---
title: ParagraphFormat.LineSpacingRule
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Paragraf için satır aralığını alır veya ayarlar.
type: docs
weight: 190
url: /tr/net/aspose.words/paragraphformat/linespacingrule/
---
## ParagraphFormat.LineSpacingRule property

Paragraf için satır aralığını alır veya ayarlar.

```csharp
public LineSpacingRule LineSpacingRule { get; set; }
```

### Örnekler

Satır aralığıyla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aşağıdaki satır aralığını kullanarak tanımlayabileceğimiz üç satır aralığı kuralı:
// paragraflar arasındaki boşluğu yapılandırmak için paragrafın "LineSpacingRule" özelliği.
// 1 - Minimum boşluk miktarını ayarlayın.
// Bu, herhangi bir boyuttaki metin satırlarına dikey dolgu verecektir
// minimum satır yüksekliğini korumak için çok küçük.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.AtLeast;
builder.ParagraphFormat.LineSpacing = 20;

builder.Writeln("Minimum line spacing of 20.");
builder.Writeln("Minimum line spacing of 20.");

// 2 - Tam aralığı ayarlayın.
// Boşluk için çok büyük olan yazı tipi boyutlarının kullanılması metni kesecektir.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Exactly;
builder.ParagraphFormat.LineSpacing = 5;

builder.Writeln("Line spacing of exactly 5.");
builder.Writeln("Line spacing of exactly 5.");

// 3 - Boşluğu, varsayılan olarak 12 punto olan varsayılan satır aralığının katı olarak ayarlayın.
// Bu tür boşluk, farklı yazı tipi boyutlarına ölçeklenir.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Multiple;
builder.ParagraphFormat.LineSpacing = 18;

builder.Writeln("Line spacing of 1.5 default lines.");
builder.Writeln("Line spacing of 1.5 default lines.");

doc.Save(ArtifactsDir + "ParagraphFormat.LineSpacing.docx");
```

### Ayrıca bakınız

* enum [LineSpacingRule](../../linespacingrule/)
* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


