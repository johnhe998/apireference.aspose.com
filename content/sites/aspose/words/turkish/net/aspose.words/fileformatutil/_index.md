---
title: Class FileFormatUtil
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.FileFormatUtil sınıf. dosya biçimini algılama veya dosya uzantılarını enums. dosya biçimine/dosya biçiminden dönüştürme gibi dosya biçimleriyle çalışmak için yardımcı yöntemler sağlar.
type: docs
weight: 2640
url: /tr/net/aspose.words/fileformatutil/
---
## FileFormatUtil class

dosya biçimini algılama veya dosya uzantılarını enums. dosya biçimine/dosya biçiminden dönüştürme gibi dosya biçimleriyle çalışmak için yardımcı yöntemler sağlar.

```csharp
public static class FileFormatUtil
```

## yöntemler

| İsim | Tanım |
| --- | --- |
| static [ContentTypeToLoadFormat](../../aspose.words/fileformatutil/contenttypetoloadformat/)(string) | IANA içerik türünü bir yükleme biçiminde numaralandırılmış değere dönüştürür. |
| static [ContentTypeToSaveFormat](../../aspose.words/fileformatutil/contenttypetosaveformat/)(string) | IANA içerik türünü, numaralandırılmış bir kaydetme biçimi değerine dönüştürür. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat)(Stream) | Bir akışta depolanan bir belgenin biçimi hakkındaki bilgileri algılar ve döndürür. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat_1)(string) | Disk dosyasında saklanan bir belgenin biçimi hakkındaki bilgileri algılar ve döndürür. |
| static [ExtensionToSaveFormat](../../aspose.words/fileformatutil/extensiontosaveformat/)(string) | Bir dosya adı uzantısını bir[`SaveFormat`](../saveformat/) değer. |
| static [ImageTypeToExtension](../../aspose.words/fileformatutil/imagetypetoextension/)(ImageType) | Aspose.Words görüntü tipi numaralandırılmış bir değeri bir dosya uzantısına dönüştürür. Döndürülen uzantı, başında nokta bulunan küçük harfli bir dizedir. |
| static [LoadFormatToExtension](../../aspose.words/fileformatutil/loadformattoextension/)(LoadFormat) | Bir yükleme biçimi numaralandırılmış değerini bir dosya uzantısına dönüştürür. Döndürülen uzantı, başında nokta bulunan küçük harfli bir dizedir. |
| static [LoadFormatToSaveFormat](../../aspose.words/fileformatutil/loadformattosaveformat/)(LoadFormat) | Bir[`LoadFormat`](../loadformat/) değer[`SaveFormat`](../saveformat/) mümkünse değer. |
| static [SaveFormatToExtension](../../aspose.words/fileformatutil/saveformattoextension/)(SaveFormat) | Bir kaydetme biçiminde numaralandırılmış değeri bir dosya uzantısına dönüştürür. Döndürülen uzantı, başında nokta bulunan küçük harfli bir dizedir. |
| static [SaveFormatToLoadFormat](../../aspose.words/fileformatutil/saveformattoloadformat/)(SaveFormat) | Bir[`SaveFormat`](../saveformat/) değer[`LoadFormat`](../loadformat/) mümkünse değer. |

### Örnekler

Bir html dosyasındaki kodlamanın nasıl algılanacağını gösterir.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// Encoding özelliği yalnızca bir html belgesi için bir FileFormatInfo nesnesi oluşturduğumuzda kullanılır.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


