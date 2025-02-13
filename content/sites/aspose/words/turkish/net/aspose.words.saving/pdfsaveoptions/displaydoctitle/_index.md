---
title: PdfSaveOptions.DisplayDocTitle
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Pencerenin başlık çubuğunun belge bilgileri sözlüğünün Başlık girişinden alınan belge başlığını gösterip göstermediğini belirten bir bayrak.
type: docs
weight: 70
url: /tr/net/aspose.words.saving/pdfsaveoptions/displaydoctitle/
---
## PdfSaveOptions.DisplayDocTitle property

Pencerenin başlık çubuğunun, belge bilgileri sözlüğünün Başlık girişinden alınan belge başlığını gösterip göstermediğini belirten bir bayrak.

```csharp
public bool DisplayDocTitle { get; set; }
```

### Notlar

Eğer`yanlış`, başlık çubuğu bunun yerine belgeyi içeren PDF dosyasının adını göstermelidir.

Bu bayrak, PDF/UA uyumluluğu için gereklidir.`doğru` değer, PDF/UA'ya kaydedilirken otomatik olarak kullanılacaktır.

Varsayılan değer`yanlış`.

### Örnekler

Belge başlığının başlık çubuğu olarak nasıl görüntüleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.BuiltInDocumentProperties.Title = "Windows bar pdf title";

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
// Adobe Acrobat Pro gibi bazı PDF okuyucularını almak için "DisplayDocTitle" öğesini "true" olarak ayarlayın,
// bu belgeye ait sekmede belgenin yerleşik "Başlık" özelliğinin değerini görüntülemek için.
// Bu tür okuyucuların belgenin dosya adını görüntülemesini sağlamak için "DisplayDocTitle" öğesini "false" olarak ayarlayın.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions { DisplayDocTitle = displayDocTitle };

doc.Save(ArtifactsDir + "PdfSaveOptions.DocTitle.pdf", pdfSaveOptions);
```

### Ayrıca bakınız

* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


