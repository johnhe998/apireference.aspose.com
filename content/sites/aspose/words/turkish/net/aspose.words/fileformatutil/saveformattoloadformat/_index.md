---
title: FileFormatUtil.SaveFormatToLoadFormat
second_title: Aspose.Words for .NET API Referansı
description: FileFormatUtil yöntem. BirSaveFormat değerLoadFormat mümkünse değer.
type: docs
weight: 90
url: /tr/net/aspose.words/fileformatutil/saveformattoloadformat/
---
## FileFormatUtil.SaveFormatToLoadFormat method

Bir[`SaveFormat`](../../saveformat/) değer[`LoadFormat`](../../loadformat/) mümkünse değer.

```csharp
public static LoadFormat SaveFormatToLoadFormat(SaveFormat saveFormat)
```

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentException | Dönüştürülemediğinde atar. |

### Örnekler

Bir kaydetme biçiminin karşılık gelen yükleme biçimine nasıl dönüştürüleceğini gösterir.

```csharp
Assert.AreEqual(LoadFormat.Html, FileFormatUtil.SaveFormatToLoadFormat(SaveFormat.Html));

// Bazı dosya türlerinde, Aspose.Words kullanılarak kaydedilmemiş ancak yüklenmemiş belgeler olabilir.
// Böyle bir türdeki kaydetme biçimini bir yükleme biçimine dönüştürmeye çalışırsak, bir istisna atılır.
Assert.Throws<ArgumentException>(() => FileFormatUtil.SaveFormatToLoadFormat(SaveFormat.Jpeg));
```

### Ayrıca bakınız

* enum [LoadFormat](../../loadformat/)
* enum [SaveFormat](../../saveformat/)
* class [FileFormatUtil](../)
* ad alanı [Aspose.Words](../../fileformatutil/)
* toplantı [Aspose.Words](../../../)


