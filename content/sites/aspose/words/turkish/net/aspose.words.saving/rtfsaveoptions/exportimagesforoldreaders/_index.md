---
title: RtfSaveOptions.ExportImagesForOldReaders
second_title: Aspose.Words for .NET API Referansı
description: RtfSaveOptions mülk. Eski okuyucular için anahtar sözcüklerin RTFye yazılıp yazılmadığını belirtir. Bu RTF belgesinin boyutunu önemli ölçüde etkileyebilir. Varsayılan değerdoğru .
type: docs
weight: 30
url: /tr/net/aspose.words.saving/rtfsaveoptions/exportimagesforoldreaders/
---
## RtfSaveOptions.ExportImagesForOldReaders property

"Eski okuyucular" için anahtar sözcüklerin RTF'ye yazılıp yazılmadığını belirtir. Bu, RTF belgesinin boyutunu önemli ölçüde etkileyebilir. Varsayılan değer:`doğru` .

```csharp
public bool ExportImagesForOldReaders { get; set; }
```

### Notlar

"Eski okuyucular" Microsoft Word 97 öncesi uygulamalar ve ayrıca WordPad. Bu seçenek seçildiğinde`doğru` Aspose.Words ek RTF anahtar sözcükleri yazar. Bu anahtar sözcükler, bir "eski okuyucu" uygulamasında açıldığında belgenin doğru şekilde görüntülenmesini sağlar, ancak belgenin boyutunu önemli ölçüde artırabilir.

Bu seçeneği ayarlarsanız`yanlış`, ardından "eski okuyucular"da yalnızca WMF, EMF ve BMP biçimlerinde görüntüler görüntülenecektir.

### Örnekler

Özel seçeneklerle bir belgenin .rtf'ye nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Bir RTF'ye kaydetme şeklimizi değiştirmek için belgenin "Kaydet" yöntemine geçmek için bir "RtfSaveOptions" nesnesi oluşturun.
RtfSaveOptions options = new RtfSaveOptions();

Assert.AreEqual(SaveFormat.Rtf, options.SaveFormat);

// "ExportCompactSize" özelliğini "true" olarak ayarlayın
// sağdan sola metin uyumluluğu pahasına kaydedilen belgenin boyutunu küçültün.
options.ExportCompactSize = true;

// Belgemizin doğru olduğundan emin olmak için fazladan anahtar kelimeler kullanmak için "ExportImagesFotOldReaders" özelliğini "true" olarak ayarlayın.
// Microsoft Word 97 öncesi okuyucular ve WordPad ile uyumludur.
// Belgenin boyutunu küçültmek için "ExportImagesFotOldReaders" özelliğini "false" olarak ayarlayın,
// ancak eski okuyucuların belgenin içerebileceği meta dosyası olmayan veya BMP görüntülerini okumasını önleyin.
options.ExportImagesForOldReaders = exportImagesForOldReaders;

doc.Save(ArtifactsDir + "RtfSaveOptions.ExportImages.rtf", options);
```

### Ayrıca bakınız

* class [RtfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../rtfsaveoptions/)
* toplantı [Aspose.Words](../../../)


