---
title: PsSaveOptions.SaveFormat
second_title: Aspose.Words for .NET API Referansı
description: PsSaveOptions mülk. Bu kaydetme seçenekleri nesnesi kullanılırsa belgenin kaydedileceği biçimi belirtir. YalnızcaPs .
type: docs
weight: 20
url: /tr/net/aspose.words.saving/pssaveoptions/saveformat/
---
## PsSaveOptions.SaveFormat property

Bu kaydetme seçenekleri nesnesi kullanılırsa belgenin kaydedileceği biçimi belirtir. YalnızcaPs .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Örnekler

Bir belgenin kitap katlama biçiminde Postscript biçiminde nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PsSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi PostScript'e dönüştürme şeklini değiştirmek için.
// İçeriği düzenlemek için "UseBookFoldPrintingSettings" özelliğini "true" olarak ayarlayın
// Çıktı Postscript belgesinde bir kitapçık yapmamıza yardımcı olacak şekilde.
// Belgeyi normal şekilde kaydetmek için "UseBookFoldPrintingSettings" özelliğini "false" olarak ayarlayın.
PsSaveOptions saveOptions = new PsSaveOptions
{
    SaveFormat = SaveFormat.Ps,
    UseBookFoldPrintingSettings = renderTextAsBookFold
};

// Belgeyi kitapçık olarak oluşturuyorsak "MultiplePages" ayarını yapmalıyız.
// "MultiplePagesType.BookFoldPrinting" için tüm bölümlerin sayfa kurulum nesnelerinin özellikleri.
foreach (Section s in doc.Sections)
{
    s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
}

// Bu belgeyi sayfaların her iki tarafına da yazdırdığımızda, tüm sayfaları bir kerede ortadan aşağı doğru katlayabiliriz,
// ve içerikler kitapçık oluşturacak şekilde sıralanacaktır.
doc.Save(ArtifactsDir + "PsSaveOptions.UseBookFoldPrintingSettings.ps", saveOptions);
```

### Ayrıca bakınız

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [PsSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pssaveoptions/)
* toplantı [Aspose.Words](../../../)


