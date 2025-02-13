---
title: Class Hyphenation
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Hyphenation sınıf. Tireleme sözlükleriyle çalışmak için yöntemler sağlar. Bu sözlükler belirli bir dildeki sözcüklerin nerede tirelenebileceğini belirtir.
type: docs
weight: 2970
url: /tr/net/aspose.words/hyphenation/
---
## Hyphenation class

Tireleme sözlükleriyle çalışmak için yöntemler sağlar. Bu sözlükler, belirli bir dildeki sözcüklerin nerede tirelenebileceğini belirtir.

```csharp
public static class Hyphenation
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| static [Callback](../../aspose.words/hyphenation/callback/) { get; set; } | Belgenin sayfa düzeni oluşturulduğunda sözlük istemek için kullanılan geri arama arabirimini alır veya ayarlar. Bu, birçok dilde belgeleri işlerken yararlı olabilecek sözlüklerin gecikmeli yüklenmesine olanak tanır. |
| static [WarningCallback](../../aspose.words/hyphenation/warningcallback/) { get; set; } | Biçimlendirme aslına uygunluk kaybına neden olabilecek bir sorun algılandığında, yükleme tireleme desenleri sırasında çağrılır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| static [IsDictionaryRegistered](../../aspose.words/hyphenation/isdictionaryregistered/)(string) | Belirtilen dil için kayıtlı sözlük yoksa veya kayıtlıysa Null sözlük ise False, aksi takdirde True döndürür. |
| static [RegisterDictionary](../../aspose.words/hyphenation/registerdictionary/#registerdictionary)(string, Stream) | Bir akıştan belirtilen dil için bir tireleme sözlüğünü kaydeder ve yükler. Sözlük okunamıyorsa veya geçersiz biçime sahipse atar. |
| static [RegisterDictionary](../../aspose.words/hyphenation/registerdictionary/#registerdictionary_1)(string, string) | Dosyadan belirtilen dil için bir tireleme sözlüğünü kaydeder ve yükler. Sözlük okunamıyorsa veya geçersiz biçime sahipse atar. |
| static [UnregisterDictionary](../../aspose.words/hyphenation/unregisterdictionary/)(string) | Belirtilen dil için bir tireleme sözlüğünün kaydını siler. |

### Örnekler

Bir dosyadan bir sözlüğün nasıl açılacağını ve kaydedileceğini gösterir.

```csharp
{
    // Tireleme sözlüğü kaydı sırasında oluşan uyarıları izleyen bir geri arama ayarlayın.
    WarningInfoCollection warningInfoCollection = new WarningInfoCollection();
    Hyphenation.WarningCallback = warningInfoCollection;

    // Akışa göre bir İngilizce (ABD) tireleme sözlüğü kaydedin.
    Stream dictionaryStream = new FileStream(MyDir + "hyph_en_US.dic", FileMode.Open);
    Hyphenation.RegisterDictionary("en-US", dictionaryStream);

    Assert.AreEqual(0, warningInfoCollection.Count);

    // Almanca gibi bir İngilizce makinede Microsoft Word'ün tireleyemeyeceği bir yerel ayara sahip bir belge açın.
    Document doc = new Document(MyDir + "German text.docx");

    // Bu belgeyi kaydettikten sonra tirelemek için "de-CH" dil kodu için bir tireleme sözlüğüne ihtiyacımız var.
    // Bu geri arama, o sözlük için otomatik isteği işleyecektir.
    Hyphenation.Callback = new CustomHyphenationDictionaryRegister();

    // Belgeyi kaydettiğimizde Almanca tireleme geçerli olacaktır.
    doc.Save(ArtifactsDir + "Hyphenation.RegisterDictionary.pdf");

    // Bu sözlük, bir uyarıyı tetikleyecek iki özdeş kalıp içerir.
    Assert.AreEqual(1, warningInfoCollection.Count);
    Assert.AreEqual(WarningType.MinorFormattingLoss, warningInfoCollection[0].WarningType);
    Assert.AreEqual(WarningSource.Layout, warningInfoCollection[0].Source);
    Assert.AreEqual("Hyphenation dictionary contains duplicate patterns. The only first found pattern will be used. " +
                    "Content can be wrapped differently.", warningInfoCollection[0].Description);
}

/// <summary>
/// Tireleme sözlüğü dosyaları için ISO dil kodlarını yerel sistem dosya adlarıyla ilişkilendirir.
/// </summary>
private class CustomHyphenationDictionaryRegister : IHyphenationCallback
{
    public CustomHyphenationDictionaryRegister()
    {
        mHyphenationDictionaryFiles = new Dictionary<string, string>
        {
            { "en-US", MyDir + "hyph_en_US.dic" },
            { "de-CH", MyDir + "hyph_de_CH.dic" }
        };
    }

    public void RequestDictionary(string language)
    {
        Console.Write("Hyphenation dictionary requested: " + language);

        if (Hyphenation.IsDictionaryRegistered(language))
        {
            Console.WriteLine(", is already registered.");
            return;
        }

        if (mHyphenationDictionaryFiles.ContainsKey(language))
        {
            Hyphenation.RegisterDictionary(language, mHyphenationDictionaryFiles[language]);
            Console.WriteLine(", successfully registered.");
            return;
        }

        Console.WriteLine(", no respective dictionary file known by this Callback.");
    }

    private readonly Dictionary<string, string> mHyphenationDictionaryFiles;
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


