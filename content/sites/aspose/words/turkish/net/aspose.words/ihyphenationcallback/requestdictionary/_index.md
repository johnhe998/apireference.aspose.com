---
title: IHyphenationCallback.RequestDictionary
second_title: Aspose.Words for .NET API Referansı
description: IHyphenationCallback yöntem. Belirtilen dil için tireleme sözlüğünün bulunamadığını ve kaydedilmesi gerekebileceğini uygulamaya bildirir.
type: docs
weight: 10
url: /tr/net/aspose.words/ihyphenationcallback/requestdictionary/
---
## IHyphenationCallback.RequestDictionary method

Belirtilen dil için tireleme sözlüğünün bulunamadığını ve kaydedilmesi gerekebileceğini uygulamaya bildirir.

Uygulama bir sözlük bulmalı ve onu kullanarak kaydetmelidir.[`RegisterDictionary`](../../hyphenation/registerdictionary/)yöntemler.

Sözlük, belirtilen dil uygulaması için kullanılamıyorsa, aynı dil için başka çağrıları devre dışı bırakabilir [`RegisterDictionary`](../../hyphenation/registerdictionary/) boş değerle.

```csharp
public void RequestDictionary(string language)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| language | String | Bir dil adı, örneğin "en-US". "Kültür adı" için .NET belgelerine ve ayrıntılar için RFC 4646'ya bakın. |

### Notlar

Bu yöntemle oluşturulan istisnalar, sayfa düzeni işleminin yürütülmesini durduracaktır.

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

* interface [IHyphenationCallback](../)
* ad alanı [Aspose.Words](../../ihyphenationcallback/)
* toplantı [Aspose.Words](../../../)


