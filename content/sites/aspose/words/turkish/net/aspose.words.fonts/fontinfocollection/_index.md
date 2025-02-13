---
title: Class FontInfoCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fonts.FontInfoCollection sınıf. Bir belgede kullanılan bir yazı tipi koleksiyonunu temsil eder.
type: docs
weight: 2750
url: /tr/net/aspose.words.fonts/fontinfocollection/
---
## FontInfoCollection class

Bir belgede kullanılan bir yazı tipi koleksiyonunu temsil eder.

```csharp
public class FontInfoCollection : IEnumerable<FontInfo>
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words.fonts/fontinfocollection/count/) { get; } | Koleksiyonda bulunan öğelerin sayısını alır. |
| [EmbedSystemFonts](../../aspose.words.fonts/fontinfocollection/embedsystemfonts/) { get; set; } | Sistem yazı tiplerinin belgeye gömülüp gömülmeyeceğini belirtir. Bu özellik için varsayılan değer **yanlış**. |
| [EmbedTrueTypeFonts](../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) { get; set; } | Bir belge kaydedildiğinde belgeye TrueType yazı tiplerinin gömülüp gömülmeyeceğini belirtir. Bu özellik için varsayılan değer **yanlış** . |
| [Item](../../aspose.words.fonts/fontinfocollection/item/) { get; } | Belirtilen ada sahip bir yazı tipi alır. (2 indexers) |
| [SaveSubsetFonts](../../aspose.words.fonts/fontinfocollection/savesubsetfonts/) { get; set; } | Belge ile katıştırılmış TrueType yazı tiplerinin bir alt kümesinin kaydedilip kaydedilmeyeceğini belirtir. Bu özellik için varsayılan değer **yanlış**. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Contains](../../aspose.words.fonts/fontinfocollection/contains/)(string) | Koleksiyonun verilen ada sahip bir yazı tipi içerip içermediğini belirler. |
| [GetEnumerator](../../aspose.words.fonts/fontinfocollection/getenumerator/)() | Koleksiyondaki tüm öğeler üzerinde yineleme yapmak için kullanılabilecek bir Numaralandırıcı nesnesi döndürür. |

### Notlar

Öğeler[`FontInfo`](../fontinfo/) nesneler.

Bu sınıfın örneklerini doğrudan oluşturmazsınız. [`FontInfos`](../../aspose.words/documentbase/fontinfos/) belgede tanımlanan yazı tiplerinin koleksiyonuna erişme özelliği.

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

* class [FontInfo](../fontinfo/)
* ad alanı [Aspose.Words.Fonts](../../aspose.words.fonts/)
* toplantı [Aspose.Words](../../)


