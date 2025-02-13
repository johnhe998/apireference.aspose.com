---
title: SaveOptions.UseAntiAliasing
second_title: Aspose.Words for .NET API Referansı
description: SaveOptions mülk. İşleme için kenar yumuşatma kullanılıp kullanılmayacağını belirleyen bir değer alır veya ayarlar.
type: docs
weight: 210
url: /tr/net/aspose.words.saving/saveoptions/useantialiasing/
---
## SaveOptions.UseAntiAliasing property

İşleme için kenar yumuşatma kullanılıp kullanılmayacağını belirleyen bir değer alır veya ayarlar.

```csharp
public bool UseAntiAliasing { get; set; }
```

### Notlar

Varsayılan değer`yanlış` . Bu değer olarak ayarlandığında`doğru` kenar yumuşatma, oluşturma için kullanılan 'dir.

Bu özellik, belge aşağıdaki biçimlerde dışa aktarıldığında kullanılır: Tiff ,Png ,Bmp , Jpeg ,Emf . Belge 'ye dışa aktarıldığındaHtml ,Mhtml veEpub biçimleri bu seçenek raster görüntüler için kullanılır.

### Örnekler

SaveOptions ile oluşturulmuş bir belgenin kalitesinin nasıl iyileştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 60;
builder.Writeln("Some text.");

SaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.Default.jpg", options);

options.UseAntiAliasing = true;
options.UseHighQualityRendering = true;

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.HighQuality.jpg", options);
```

### Ayrıca bakınız

* class [SaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../saveoptions/)
* toplantı [Aspose.Words](../../../)


