---
title: DocumentBase.FontInfos
second_title: Aspose.Words for .NET API Referansı
description: DocumentBase mülk. Bu belgede kullanılan yazı tiplerinin özelliklerine erişim sağlar.
type: docs
weight: 30
url: /tr/net/aspose.words/documentbase/fontinfos/
---
## DocumentBase.FontInfos property

Bu belgede kullanılan yazı tiplerinin özelliklerine erişim sağlar.

```csharp
public FontInfoCollection FontInfos { get; }
```

### Notlar

Bu yazı tipi tanımları koleksiyonu, belgeden olduğu gibi yüklenir. Bazı belgelerde yazı tipi tanımları isteğe bağlı, eksik veya eksik olabilir.

Belgede belirli bir yazı tipinin kullanıldığını belirlemek için bu koleksiyona güvenmeyin. Bu koleksiyonu yalnızca belgede kullanılabilecek yazı tipleri hakkında bilgi almak için kullanmalısınız.

### Örnekler

Bir belgede hangi yazı tiplerinin bulunduğunun ayrıntılarının nasıl yazdırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Belgedeki tüm kullanılmış ve kullanılmayan yazı tiplerini yazdırın.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

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

* class [FontInfoCollection](../../../aspose.words.fonts/fontinfocollection/)
* class [DocumentBase](../)
* ad alanı [Aspose.Words](../../documentbase/)
* toplantı [Aspose.Words](../../../)


