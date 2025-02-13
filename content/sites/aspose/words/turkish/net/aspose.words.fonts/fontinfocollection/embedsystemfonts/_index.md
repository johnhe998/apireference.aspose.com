---
title: FontInfoCollection.EmbedSystemFonts
second_title: Aspose.Words for .NET API Referansı
description: FontInfoCollection mülk. Sistem yazı tiplerinin belgeye gömülüp gömülmeyeceğini belirtir. Bu özellik için varsayılan değer yanlış.
type: docs
weight: 20
url: /tr/net/aspose.words.fonts/fontinfocollection/embedsystemfonts/
---
## FontInfoCollection.EmbedSystemFonts property

Sistem yazı tiplerinin belgeye gömülüp gömülmeyeceğini belirtir. Bu özellik için varsayılan değer **yanlış**.

Bu seçenek yalnızca şu durumlarda çalışır:[`EmbedTrueTypeFonts`](../embedtruetypefonts/) seçenek olarak ayarlandı **doğru**.

```csharp
public bool EmbedSystemFonts { get; set; }
```

### Notlar

Bu özelliğin ayarlanması`Doğru`kullanıcı bir Doğu Asya system üzerindeyse ve sistemlerinde that dili için yazı tiplerine sahip olmayan başkaları tarafından okunabilen bir belge oluşturmak istiyorsa yararlıdır. Örneğin, bir Japon sistemindeki bir kullanıcı, Japonca belgenin tüm sistemlerde okunabilmesi için yazı tiplerini bir belgeye gömmeyi seçebilir.

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


