---
title: Font.TintAndShade
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Bir rengi açan veya koyulaştıran bir çift değer alır veya ayarlar.
type: docs
weight: 520
url: /tr/net/aspose.words/font/tintandshade/
---
## Font.TintAndShade property

Bir rengi açan veya koyulaştıran bir çift değer alır veya ayarlar.

```csharp
public double TintAndShade { get; set; }
```

### Notlar

Bu özellik için izin verilen değerler -1 (en koyu) ile 1 (en açık) aralığındadır. Sıfır (0) nötrdür. Bu özelliği -1'den küçük veya 1 değerinden büyük bir değere ayarlamaya çalışmak,ArgumentOutOfRangeException.

Bu özelliğin, teması olmayan color ile Font nesnesi için ayarlanması, birInvalidOperationException.

### Örnekler

Temalı stilin nasıl oluşturulacağını ve kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Tema yazı tipi özellikleriyle bir stil oluşturun.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

### Ayrıca bakınız

* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


