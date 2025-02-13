---
title: PclSaveOptions.FallbackFontName
second_title: Aspose.Words for .NET API Referansı
description: PclSaveOptions mülk. Yazıcı ve yerleşik yazı tipi koleksiyonlarında beklenen yazı tipi bulunmazsa kullanılacak yazı tipinin adı .
type: docs
weight: 20
url: /tr/net/aspose.words.saving/pclsaveoptions/fallbackfontname/
---
## PclSaveOptions.FallbackFontName property

Yazıcı ve yerleşik yazı tipi koleksiyonlarında beklenen yazı tipi bulunmazsa kullanılacak yazı tipinin adı .

```csharp
public string FallbackFontName { get; set; }
```

### Notlar

Geri dönüş bulunamazsa bir uyarı oluşturulur ve "Arial" yazı tipi kullanılır.

### Örnekler

Orijinal yazı tipi kullanılamıyorsa, yazıcının yazdırılan metne yedek olarak uygulayacağı bir yazı tipinin nasıl bildirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.FallbackFontName = "Times New Roman";

// Bu belge, yazıcıya eksik yazı tipine sahip metne "Times New Roman" uygulaması talimatını verecektir.
// "Times New Roman" da kullanılamıyorsa, yazıcı varsayılan olarak "Arial" yazı tipini kullanır.
doc.Save(ArtifactsDir + "PclSaveOptions.SetPrinterFont.pcl", saveOptions);
```

### Ayrıca bakınız

* class [PclSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pclsaveoptions/)
* toplantı [Aspose.Words](../../../)


