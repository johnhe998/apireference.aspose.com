---
title: HtmlSaveOptions.ExportTextInputFormFieldAsText
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Metin girişi form alanlarının HTML veya MHTMLye nasıl kaydedileceğini kontrol eder. Varsayılan değeryanlış .
type: docs
weight: 270
url: /tr/net/aspose.words.saving/htmlsaveoptions/exporttextinputformfieldastext/
---
## HtmlSaveOptions.ExportTextInputFormFieldAsText property

Metin girişi form alanlarının HTML veya MHTML'ye nasıl kaydedileceğini kontrol eder. Varsayılan değer`yanlış` .

```csharp
public bool ExportTextInputFormFieldAsText { get; set; }
```

### Notlar

olarak ayarlandığında`doğru` , metin girişi form alanlarını normal metin olarak dışa aktarır. Ne zaman`yanlış`, Word metin girişi form alanlarını HTML'de GİRİŞ öğeleri olarak dışa aktarır.

EPUB'a dışa aktarırken, metin girişi form alanları, bu biçimin gereksinimlerine nedeniyle her zaman metin olarak kaydedilir.

### Örnekler

.html'ye kaydettikten sonra bağlantılı görüntülerin saklanacağı klasörün nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// Form alanlarını HTML giriş öğeleri yerine düz metin olarak dışa aktarma seçeneği ayarlayın.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


