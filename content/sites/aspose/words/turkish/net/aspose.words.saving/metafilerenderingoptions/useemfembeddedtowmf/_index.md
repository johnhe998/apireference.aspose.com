---
title: MetafileRenderingOptions.UseEmfEmbeddedToWmf
second_title: Aspose.Words for .NET API Referansı
description: MetafileRenderingOptions mülk. Gömülü EMF meta dosyalarına sahip WMF meta dosyalarının nasıl işleneceğini belirleyen bir değer alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.saving/metafilerenderingoptions/useemfembeddedtowmf/
---
## MetafileRenderingOptions.UseEmfEmbeddedToWmf property

Gömülü EMF meta dosyalarına sahip WMF meta dosyalarının nasıl işleneceğini belirleyen bir değer alır veya ayarlar.

```csharp
public bool UseEmfEmbeddedToWmf { get; set; }
```

### Notlar

WMF meta dosyaları, gömülü EMF verilerini içerebilir. MS Word çoğu durumda gömülü EMF verilerini kullanır. GDI+ her zaman WMF verilerini kullanır.

Bu değer olarak ayarlandığında`doğru`, Aspose.Words, oluşturma sırasında gömülü EMF verilerini kullanır.

Bu değer olarak ayarlandığında`yanlış`, Aspose.Words, oluştururken WMF verilerini kullanır.

Bu seçenek yalnızca meta dosyası vektör grafikleri olarak işlendiğinde kullanılır. Meta dosyası bitmap'e işlendiğinde, her zaman WMF verileri kullanılır.

Varsayılan değer`doğru`.

### Örnekler

PDF'ye kaydederken Gelişmiş Windows Meta Dosyası ile ilgili işleme seçeneklerinin nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "EMF.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// "EmfPlusDualRenderingMode" özelliğini "EmfPlusDualRenderingMode.Emf" olarak ayarlayın
// bir EMF+ ikili meta dosyasının yalnızca EMF bölümünü oluşturmak için.
// "EmfPlusDualRenderingMode" özelliğini "EmfPlusDualRenderingMode.EmfPlus" olarak ayarlayın.
// bir EMF+ ikili meta dosyasının EMF+ bölümünü oluşturmak için.
// "EmfPlusDualRenderingMode" özelliğini "EmfPlusDualRenderingMode.EmfPlusWithFallback" olarak ayarlayın
// EMF+ kayıtlarının tümü destekleniyorsa, bir EMF+ ikili meta dosyasının EMF+ bölümünü oluşturmak için.
// Aksi takdirde Aspose.Words EMF kısmını oluşturacaktır.
saveOptions.MetafileRenderingOptions.EmfPlusDualRenderingMode = renderingMode;

// Gömülü EMF verilerini işlemek için "UseEmfEmbeddedToWmf" özelliğini "true" olarak ayarlayın
// vektör grafikleri olarak oluşturabileceğimiz meta dosyalar için.
saveOptions.MetafileRenderingOptions.UseEmfEmbeddedToWmf = true;

doc.Save(ArtifactsDir + "PdfSaveOptions.RenderMetafile.pdf", saveOptions);
```

### Ayrıca bakınız

* class [MetafileRenderingOptions](../)
* ad alanı [Aspose.Words.Saving](../../metafilerenderingoptions/)
* toplantı [Aspose.Words](../../../)


