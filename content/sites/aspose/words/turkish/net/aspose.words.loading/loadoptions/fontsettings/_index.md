---
title: LoadOptions.FontSettings
second_title: Aspose.Words for .NET API Referansı
description: LoadOptions mülk. Belge yazı tipi ayarlarını belirlemeye izin verir.
type: docs
weight: 70
url: /tr/net/aspose.words.loading/loadoptions/fontsettings/
---
## LoadOptions.FontSettings property

Belge yazı tipi ayarlarını belirlemeye izin verir.

```csharp
public FontSettings FontSettings { get; set; }
```

### Notlar

Bazı formatlar yüklenirken Aspose.Words yazı tiplerini çözümlemeyi gerektirebilir. Örneğin, HTML belgelerini yüklerken Aspose.Words , font geri dönüşünü gerçekleştirmek için fontları çözebilir.

Null olarak ayarlanırsa, varsayılan statik yazı tipi ayarları[`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) kullanılacak.

Varsayılan değer null'dur.

### Örnekler

Bir belge yüklenirken yazı tipi değiştirme ayarlarının nasıl uygulanacağını gösterir.

```csharp
// "Times New Roman" yazı tipinin yerini alacak bir FontSettings nesnesi oluşturun
// "MyFonts" klasörümüzden "Arvo" yazı tipi ile.
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(FontsDir, false);
fontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Times New Roman", "Arvo");

// FontSettings nesnesini yeni oluşturulan bir LoadOptions nesnesinin özelliği olarak ayarlayın.
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;

// Belgeyi yükleyin, ardından yazı tipi değişikliği ile PDF olarak oluşturun.
Document doc = new Document(MyDir + "Document.docx", loadOptions);

doc.Save(ArtifactsDir + "LoadOptions.FontSettings.pdf");
```

Yükleme sırasında yazı tipi ikamelerinin nasıl belirleneceğini gösterir.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();

// LoadOptions nesnesi için bir yazı tipi değiştirme kuralı ayarlayın.
// Yüklediğimiz belge bizde olmayan bir yazı tipi kullanıyorsa,
// bu kural, mevcut olmayan yazı tipini mevcut olanla değiştirecektir.
// Bu durumda, "MissingFont"un tüm kullanımları "Comic Sans MS"e dönüşecektir.
TableSubstitutionRule substitutionRule = loadOptions.FontSettings.SubstitutionSettings.TableSubstitution;
substitutionRule.AddSubstitutes("MissingFont", new[] {"Comic Sans MS"});

Document doc = new Document(MyDir + "Missing font.html", loadOptions);

// Bu noktada böyle bir metin hala "MissingFont" içinde olacaktır.
// Belgeyi render ettiğimizde font değişimi gerçekleşecektir.
Assert.AreEqual("MissingFont", doc.FirstSection.Body.FirstParagraph.Runs[0].Font.Name);

doc.Save(ArtifactsDir + "FontSettings.ResolveFontsBeforeLoadingDocument.pdf");
```

### Ayrıca bakınız

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [LoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../loadoptions/)
* toplantı [Aspose.Words](../../../)


