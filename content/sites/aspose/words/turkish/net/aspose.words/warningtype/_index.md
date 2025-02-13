---
title: Enum WarningType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.WarningType Sıralama. Belge yükleme veya kaydetme sırasında Aspose.Words tarafından verilen uyarının türünü belirtir.
type: docs
weight: 6350
url: /tr/net/aspose.words/warningtype/
---
## WarningType enumeration

Belge yükleme veya kaydetme sırasında Aspose.Words tarafından verilen uyarının türünü belirtir.

```csharp
[Flags]
public enum WarningType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| DataLossCategory | `FF` | Yüklemeden sonra belge ağacında, veya kaydetme sonrasında oluşturulan belgede bazı metin/karakter/resim veya diğer veriler eksik olacaktır. |
| DataLoss | `1` | Genel veri kaybı, belirli bir kod yok. |
| MajorFormattingLossCategory | `FF00` | Ortaya çıkan belge veya içindeki belirli bir konum, orijinal belgeyle karşılaştırıldığında önemli ölçüde farklı görünebilir. |
| MajorFormattingLoss | `100` | Genel ana biçimlendirme kaybı, belirli bir kod yok. |
| MinorFormattingLossCategory | `FF0000` | Ortaya çıkan belge veya içindeki belirli bir konum, orijinal belgeyle karşılaştırıldığında biraz farklı görünebilir. |
| MinorFormattingLoss | `10000` | Genel küçük biçimlendirme kaybı, belirli bir kod yok. |
| FontSubstitution | `20000` | Yazı tipi değiştirildi. |
| FontEmbedding | `40000` | Belge kaydetme sırasında gömülü yazı tipi bilgisi kaybı. |
| UnexpectedContentCategory | `F000000` | Kaynak belgedeki bazı içerik tanınamadı (yani desteklenmiyor), bu sorunlara neden olabilir veya olmayabilir veya veri/biçimlendirme kaybına neden olabilir. |
| UnexpectedContent | `1000000` | Genel beklenmeyen içerik, belirli bir kod yok. |
| Hint | `10000000` | Olası bir sorunla ilgili tavsiyede bulunur veya bir iyileştirme önerir. |

### Örnekler

Mevcut yazı tipi kaynaklarından eksik bir yazı tipi için en yakın eşleşmeyi bulma özelliğinin nasıl ayarlanacağını gösterir.

```csharp
[Test]
public void EnableFontSubstitution()
{
    // Yazı tipi kaynaklarımızın hiçbirinde bulunmayan bir yazı tipiyle biçimlendirilmiş metin içeren bir belge açın.
    Document doc = new Document(MyDir + "Missing font.docx");

    // Yazı tipi değiştirme uyarılarını işlemek için bir geri arama atayın.
    HandleDocumentSubstitutionWarnings substitutionWarningHandler = new HandleDocumentSubstitutionWarnings();
    doc.WarningCallback = substitutionWarningHandler;

    // Varsayılan bir yazı tipi adı ayarlayın ve yazı tipi değiştirmeyi etkinleştirin.
    FontSettings fontSettings = new FontSettings();
    fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
    ;
    fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;

    // Yazı tipi eksik olan bir belgeyi kaydedersek yazı tipi değiştirme uyarısı alırız.
    doc.FontSettings = fontSettings;
    doc.Save(ArtifactsDir + "FontSettings.EnableFontSubstitution.pdf");

    using (IEnumerator<WarningInfo> warnings = substitutionWarningHandler.FontWarnings.GetEnumerator())
        while (warnings.MoveNext())
            Console.WriteLine(warnings.Current.Description);

    // Ayrıca koleksiyondaki uyarıları doğrulayabilir ve temizleyebiliriz.
    Assert.AreEqual(WarningSource.Layout, substitutionWarningHandler.FontWarnings[0].Source);
    Assert.AreEqual(
        "Font '28 Days Later' has not been found. Using 'Calibri' font instead. Reason: alternative name from document.",
        substitutionWarningHandler.FontWarnings[0].Description);

    substitutionWarningHandler.FontWarnings.Clear();

    Assert.That(substitutionWarningHandler.FontWarnings, Is.Empty);
}

public class HandleDocumentSubstitutionWarnings : IWarningCallback
{
    /// <summary>
    /// Yükleme/kaydetme sırasında her uyarı oluştuğunda çağrılır.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


