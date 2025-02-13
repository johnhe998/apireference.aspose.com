---
title: FileFormatUtil.ContentTypeToLoadFormat
second_title: Aspose.Words for .NET API Referansı
description: FileFormatUtil yöntem. IANA içerik türünü bir yükleme biçiminde numaralandırılmış değere dönüştürür.
type: docs
weight: 10
url: /tr/net/aspose.words/fileformatutil/contenttypetoloadformat/
---
## FileFormatUtil.ContentTypeToLoadFormat method

IANA içerik türünü bir yükleme biçiminde numaralandırılmış değere dönüştürür.

```csharp
public static LoadFormat ContentTypeToLoadFormat(string contentType)
```

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentException | Dönüştürülemediğinde atar. |

### Örnekler

Her ortam türü dizesinden ilgili Aspose yükle/kaydet biçiminin nasıl bulunacağını gösterir.

```csharp
// ContentTypeToSaveFormat/ContentTypeToLoadFormat yöntemleri yalnızca MIME türleri olarak da bilinen resmi IANA medya türü adlarını kabul eder. 
// Tüm geçerli medya türleri burada listelenmiştir: https://www.iana.org/assignments/media-types/media-types.xhtml.

// Bir SaveFormat'ı kısmi ortam türü dizesiyle ilişkilendirmeye çalışmak işe yaramaz.
Assert.Throws<ArgumentException>(() => FileFormatUtil.ContentTypeToSaveFormat("jpeg"));

// Aspose.Words'ün bir içerik türü için karşılık gelen bir kaydetme/yükleme formatı yoksa, bir istisna da atılacaktır.
Assert.Throws<ArgumentException>(() => FileFormatUtil.ContentTypeToSaveFormat("application/zip"));

// Aşağıda listelenen türlerdeki dosyalar kaydedilebilir ancak Aspose.Words kullanılarak yüklenemez.
Assert.Throws<ArgumentException>(() => FileFormatUtil.ContentTypeToLoadFormat("image/jpeg"));

Assert.AreEqual(SaveFormat.Jpeg, FileFormatUtil.ContentTypeToSaveFormat("image/jpeg"));
Assert.AreEqual(SaveFormat.Png, FileFormatUtil.ContentTypeToSaveFormat("image/png"));
Assert.AreEqual(SaveFormat.Tiff, FileFormatUtil.ContentTypeToSaveFormat("image/tiff"));
Assert.AreEqual(SaveFormat.Gif, FileFormatUtil.ContentTypeToSaveFormat("image/gif"));
Assert.AreEqual(SaveFormat.Emf, FileFormatUtil.ContentTypeToSaveFormat("image/x-emf"));
Assert.AreEqual(SaveFormat.Xps, FileFormatUtil.ContentTypeToSaveFormat("application/vnd.ms-xpsdocument"));
Assert.AreEqual(SaveFormat.Pdf, FileFormatUtil.ContentTypeToSaveFormat("application/pdf"));
Assert.AreEqual(SaveFormat.Svg, FileFormatUtil.ContentTypeToSaveFormat("image/svg+xml"));
Assert.AreEqual(SaveFormat.Epub, FileFormatUtil.ContentTypeToSaveFormat("application/epub+zip"));

// Kaydedilebilen ve yüklenebilen dosya türleri için bir medya türünü hem yükleme biçimiyle hem de kaydetme biçimiyle eşleştirebiliriz.
Assert.AreEqual(LoadFormat.Doc, FileFormatUtil.ContentTypeToLoadFormat("application/msword"));
Assert.AreEqual(SaveFormat.Doc, FileFormatUtil.ContentTypeToSaveFormat("application/msword"));

Assert.AreEqual(LoadFormat.Docx,
    FileFormatUtil.ContentTypeToLoadFormat(
        "application/vnd.openxmlformats-officedocument.wordprocessingml.document"));
Assert.AreEqual(SaveFormat.Docx,
    FileFormatUtil.ContentTypeToSaveFormat(
        "application/vnd.openxmlformats-officedocument.wordprocessingml.document"));

Assert.AreEqual(LoadFormat.Text, FileFormatUtil.ContentTypeToLoadFormat("text/plain"));
Assert.AreEqual(SaveFormat.Text, FileFormatUtil.ContentTypeToSaveFormat("text/plain"));

Assert.AreEqual(LoadFormat.Rtf, FileFormatUtil.ContentTypeToLoadFormat("application/rtf"));
Assert.AreEqual(SaveFormat.Rtf, FileFormatUtil.ContentTypeToSaveFormat("application/rtf"));

Assert.AreEqual(LoadFormat.Html, FileFormatUtil.ContentTypeToLoadFormat("text/html"));
Assert.AreEqual(SaveFormat.Html, FileFormatUtil.ContentTypeToSaveFormat("text/html"));

Assert.AreEqual(LoadFormat.Mhtml, FileFormatUtil.ContentTypeToLoadFormat("multipart/related"));
Assert.AreEqual(SaveFormat.Mhtml, FileFormatUtil.ContentTypeToSaveFormat("multipart/related"));
```

### Ayrıca bakınız

* enum [LoadFormat](../../loadformat/)
* class [FileFormatUtil](../)
* ad alanı [Aspose.Words](../../fileformatutil/)
* toplantı [Aspose.Words](../../../)


