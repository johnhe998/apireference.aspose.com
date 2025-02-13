---
title: SaveOptions.UseHighQualityRendering
second_title: Aspose.Words for .NET API Referansı
description: SaveOptions mülk. Yüksek kaliteli yani yavaş işleme algoritmalarının kullanılıp kullanılmayacağını belirleyen bir değer alır veya ayarlar.
type: docs
weight: 220
url: /tr/net/aspose.words.saving/saveoptions/usehighqualityrendering/
---
## SaveOptions.UseHighQualityRendering property

Yüksek kaliteli (yani yavaş) işleme algoritmalarının kullanılıp kullanılmayacağını belirleyen bir değer alır veya ayarlar.

```csharp
public bool UseHighQualityRendering { get; set; }
```

### Notlar

Varsayılan değer`yanlış` .

Bu özellik, belge görüntü biçimlerine dışa aktarıldığında kullanılır: Tiff ,Png ,Bmp , Jpeg ,Emf.

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


