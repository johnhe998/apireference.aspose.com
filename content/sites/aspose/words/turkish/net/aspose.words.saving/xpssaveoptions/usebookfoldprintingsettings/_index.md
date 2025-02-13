---
title: XpsSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words for .NET API Referansı
description: XpsSaveOptions mülk. Belgenin bir kitapçık yazdırma düzeni kullanılarak kaydedilmesi gerekip gerekmediğini belirten bir boole değeri alır veya ayarlar aracılığıyla belirtilirseMultiplePages .
type: docs
weight: 40
url: /tr/net/aspose.words.saving/xpssaveoptions/usebookfoldprintingsettings/
---
## XpsSaveOptions.UseBookFoldPrintingSettings property

Belgenin bir kitapçık yazdırma düzeni kullanılarak kaydedilmesi gerekip gerekmediğini belirten bir boole değeri alır veya ayarlar, aracılığıyla belirtilirse[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### Notlar

Bu seçenek belirtilirse,[`PageSet`](../../fixedpagesaveoptions/pageset/) kaydederken yok sayılır. Bu davranış MS Word ile eşleşir. Sayfa ayarında kitap katlama yazdırma ayarları belirtilmezse, bu seçeneğin hiçbir etkisi olmaz.

### Örnekler

Bir belgenin kitap katlama biçiminde XPS biçiminde nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "XpsSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .XPS'ye dönüştürme şeklini değiştirmek için.
XpsSaveOptions xpsOptions = new XpsSaveOptions(SaveFormat.Xps);

// İçeriği düzenlemek için "UseBookFoldPrintingSettings" özelliğini "true" olarak ayarlayın
// çıktıda XPS'yi kitapçık yapmak için kullanmamıza yardımcı olacak şekilde.
// XPS'yi normal şekilde işlemek için "UseBookFoldPrintingSettings" özelliğini "false" olarak ayarlayın.
xpsOptions.UseBookFoldPrintingSettings = renderTextAsBookFold;

// Belgeyi kitapçık olarak oluşturuyorsak "MultiplePages" ayarını yapmalıyız.
// "MultiplePagesType.BookFoldPrinting" için tüm bölümlerin sayfa kurulum nesnelerinin özellikleri.
if (renderTextAsBookFold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// Bu belgeyi yazdırdıktan sonra sayfaları üst üste dizerek kitapçık haline getirebiliriz
// yazıcıdan çıkmak ve ortadan katlamak için.
doc.Save(ArtifactsDir + "XpsSaveOptions.BookFold.xps", xpsOptions);
```

### Ayrıca bakınız

* class [XpsSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../xpssaveoptions/)
* toplantı [Aspose.Words](../../../)


