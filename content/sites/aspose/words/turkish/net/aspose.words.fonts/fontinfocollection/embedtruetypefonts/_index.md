---
title: FontInfoCollection.EmbedTrueTypeFonts
second_title: Aspose.Words for .NET API Referansı
description: FontInfoCollection mülk. Bir belge kaydedildiğinde belgeye TrueType yazı tiplerinin gömülüp gömülmeyeceğini belirtir. Bu özellik için varsayılan değer yanlış .
type: docs
weight: 30
url: /tr/net/aspose.words.fonts/fontinfocollection/embedtruetypefonts/
---
## FontInfoCollection.EmbedTrueTypeFonts property

Bir belge kaydedildiğinde belgeye TrueType yazı tiplerinin gömülüp gömülmeyeceğini belirtir. Bu özellik için varsayılan değer **yanlış** .

```csharp
public bool EmbedTrueTypeFonts { get; set; }
```

### Notlar

TrueType yazı tiplerini gömmek, başkalarının belgeyi, onu oluşturmak için kullanılanla aynı yazı tipleriyle görüntülemesine olanak tanır, , ancak belge boyutunu önemli ölçüde artırabilir.

Bu seçenek yalnızca DOC, DOCX ve RTF biçimleri için çalışır.

### Örnekler

Bir belgenin gömülü TrueType yazı tipleriyle nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Ayrıca bakınız

* class [FontInfoCollection](../)
* ad alanı [Aspose.Words.Fonts](../../fontinfocollection/)
* toplantı [Aspose.Words](../../../)


