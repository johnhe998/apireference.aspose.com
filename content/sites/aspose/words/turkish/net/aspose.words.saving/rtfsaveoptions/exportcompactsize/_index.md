---
title: RtfSaveOptions.ExportCompactSize
second_title: Aspose.Words for .NET API Referansı
description: RtfSaveOptions mülk. Çıktı RTF belgelerini boyut olarak küçültmeye izin verir ancak RTL sağdan sola metin içeriyorsa doğru şekilde görüntülenmez. Varsayılan değeryanlış .
type: docs
weight: 20
url: /tr/net/aspose.words.saving/rtfsaveoptions/exportcompactsize/
---
## RtfSaveOptions.ExportCompactSize property

Çıktı RTF belgelerini boyut olarak küçültmeye izin verir, ancak RTL (sağdan sola) metin içeriyorsa, doğru şekilde görüntülenmez. Varsayılan değer`yanlış` .

```csharp
public bool ExportCompactSize { get; set; }
```

### Notlar

Aspose.Words kullanarak RTF'ye dönüştürmek istediğiniz belge, Arapça gibi dillerde sağdan sola metin içermiyorsa, bu seçeneği şu şekilde ayarlayabilirsiniz:`doğru` elde edilen RTF'nin boyutunu küçültmek için.

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


