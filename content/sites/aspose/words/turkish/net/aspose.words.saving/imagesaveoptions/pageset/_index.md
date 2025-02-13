---
title: ImageSaveOptions.PageSet
second_title: Aspose.Words for .NET API Referansı
description: ImageSaveOptions mülk. Oluşturulacak sayfaları alır veya ayarlar. Varsayılan belgedeki tüm sayfalardır.
type: docs
weight: 90
url: /tr/net/aspose.words.saving/imagesaveoptions/pageset/
---
## ImageSaveOptions.PageSet property

Oluşturulacak sayfaları alır veya ayarlar. Varsayılan, belgedeki tüm sayfalardır.

```csharp
public PageSet PageSet { get; set; }
```

### Notlar

Bu özellik yalnızca belge sayfaları oluşturulurken etkilidir. Bu özellik, şekiller resimlere dönüştürülürken yok sayılır.

### Örnekler

Tam sayfa aralıklarına göre sayfaların nasıl ayıklanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");

ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Tiff);
PageSet pageSet = new PageSet(new PageRange(1, 1), new PageRange(2, 3), new PageRange(1, 3),
    new PageRange(2, 4), new PageRange(1, 1));

imageOptions.PageSet = pageSet;
doc.Save(ArtifactsDir + "ImageSaveOptions.ExportVariousPageRanges.tiff", imageOptions);
```

Bir belgenin her sayfasının ayrı bir TIFF görüntüsüne nasıl işleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "ImageSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi bir görüntüye dönüştürme şeklini değiştirmek için.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);

for (int i = 0; i < doc.PageCount; i++)
{
    // "PageSet" özelliğini ilk sayfanın numarasına ayarlayın
    // belgeyi oluşturmaya başlamak için.
    options.PageSet = new PageSet(i);

    doc.Save(ArtifactsDir + $"ImageSaveOptions.PageByPage.{i + 1}.tiff", options);
}
```

Bir belgedeki hangi sayfanın görüntü olarak oluşturulacağını nasıl belirtileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world! This is page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("This is page 3.");

Assert.AreEqual(3, doc.PageCount);

// Belgeyi resim olarak kaydettiğimizde Aspose.Words varsayılan olarak sadece ilk sayfayı oluşturuyor.
// Oluşturulacak farklı bir sayfa belirtmek için bir SaveOptions nesnesi iletebiliriz.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Gif);

// Belgenin her sayfasını ayrı bir resim dosyasına işleyin.
for (int i = 1; i <= doc.PageCount; i++)
{
    saveOptions.PageSet = new PageSet(1);

    doc.Save(ArtifactsDir + $"ImageSaveOptions.PageIndex.Page {i}.gif", saveOptions);
}
```

Bir belgeden bir sayfanın bir JPEG görüntüsüne nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "ImageSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi bir görüntüye dönüştürme şeklini değiştirmek için.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// aracılığıyla ikinci sayfayı seçmek için "PageSet"i "1" olarak ayarlayın.
// belgeyi oluşturmaya başlamak için sıfır tabanlı dizin.
options.PageSet = new PageSet(1);

// Belgeyi JPEG formatında kaydettiğimizde Aspose.Words sadece bir sayfa oluşturuyor.
// Bu resim ikinci sayfadan başlayarak bir sayfa içerecek,
// orijinal belgenin sadece ikinci sayfası olacak.
doc.Save(ArtifactsDir + "ImageSaveOptions.OnePage.jpg", options);
```

### Ayrıca bakınız

* class [PageSet](../../pageset/)
* class [ImageSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../imagesaveoptions/)
* toplantı [Aspose.Words](../../../)


