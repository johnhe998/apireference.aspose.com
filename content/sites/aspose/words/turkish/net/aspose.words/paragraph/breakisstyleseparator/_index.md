---
title: Paragraph.BreakIsStyleSeparator
second_title: Aspose.Words for .NET API Referansı
description: Paragraph mülk. Bu paragraf sonu bir Stil Ayırıcı ise doğrudur. Stil ayırıcı one paragrafın farklı paragraf stillerine sahip parçalardan oluşmasına izin verir.
type: docs
weight: 20
url: /tr/net/aspose.words/paragraph/breakisstyleseparator/
---
## Paragraph.BreakIsStyleSeparator property

Bu paragraf sonu bir Stil Ayırıcı ise doğrudur. Stil ayırıcı, one paragrafın farklı paragraf stillerine sahip parçalardan oluşmasına izin verir.

```csharp
public bool BreakIsStyleSeparator { get; }
```

### Örnekler

İçindekiler başlığıyla aynı satıra nasıl metin yazılacağını ve İçindekiler'de görünmemesini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTableOfContents("\\o \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// İçindekiler'in giriş olarak alacağı bir stile sahip bir paragraf ekleyin.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

// Bu dizelerin her ikisi de aynı paragraftadır ve bu nedenle aynı TOC girişinde görünecektir.
builder.Write("Heading 1. ");
builder.Write("Will appear in the TOC. ");

// Bir stil ayırıcı eklersek, aynı paragrafa daha fazla metin yazabiliriz
// ve TOC'de görünmeden farklı bir stil kullanın.
// Ayırıcıdan sonra bir başlık tipi stili kullanırsak, bir belge metin satırından birden fazla TOC girişi çizebiliriz.
builder.InsertStyleSeparator();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Quote;
builder.Write("Won't appear in the TOC. ");

Assert.True(doc.FirstSection.Body.FirstParagraph.BreakIsStyleSeparator);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Paragraph.BreakIsStyleSeparator.docx");
```

### Ayrıca bakınız

* class [Paragraph](../)
* ad alanı [Aspose.Words](../../paragraph/)
* toplantı [Aspose.Words](../../../)


