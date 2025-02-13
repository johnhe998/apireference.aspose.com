---
title: ImageData.SetImage
second_title: Aspose.Words for .NET API Referansı
description: ImageData yöntem. Şeklin gösterdiği görüntüyü ayarlar.
type: docs
weight: 200
url: /tr/net/aspose.words.drawing/imagedata/setimage/
---
## SetImage(Image) {#setimage}

Şeklin gösterdiği görüntüyü ayarlar.

```csharp
public void SetImage(Image image)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| image | Image | Görüntü nesnesi. |

### Örnekler

Bir belgede yerel dosya sisteminden görüntülerin nasıl görüntüleneceğini gösterir.

```csharp
Document doc = new Document();

// Bir belgede bir resmi görüntülemek için bir şekil oluşturmamız gerekecek
// bir görüntü içerecek ve ardından onu belgenin gövdesine ekleyecektir.
Shape imgShape;

// Aşağıda, yerel dosya sistemindeki bir dosyadan görüntü almanın iki yolu bulunmaktadır.
// 1 - Bir görüntü dosyasından bir görüntü nesnesi oluşturun:
using (Image srcImage = Image.FromFile(ImageDir + "Logo.jpg"))
{
    imgShape = new Shape(doc, ShapeType.Image);
    doc.FirstSection.Body.FirstParagraph.AppendChild(imgShape);
    imgShape.ImageData.SetImage(srcImage);
}

// 2 - Bir akış kullanarak yerel dosya sisteminden bir görüntü dosyası açın:
using (Stream stream = new FileStream(ImageDir + "Logo.jpg", FileMode.Open, FileAccess.Read))
{
    imgShape = new Shape(doc, ShapeType.Image);
    doc.FirstSection.Body.FirstParagraph.AppendChild(imgShape);
    imgShape.ImageData.SetImage(stream);
    imgShape.Left = 150.0f;
}

doc.Save(ArtifactsDir + "Drawing.ImportImage.docx");
```

### Ayrıca bakınız

* class [ImageData](../)
* ad alanı [Aspose.Words.Drawing](../../imagedata/)
* toplantı [Aspose.Words](../../../)

---

## SetImage(Stream) {#setimage_1}

Şeklin gösterdiği görüntüyü ayarlar.

```csharp
public void SetImage(Stream stream)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| stream | Stream | Resmi içeren akış. |

### Örnekler

Bir belgede yerel dosya sisteminden görüntülerin nasıl görüntüleneceğini gösterir.

```csharp
Document doc = new Document();

// Bir belgede bir resmi görüntülemek için bir şekil oluşturmamız gerekecek
// bir görüntü içerecek ve ardından onu belgenin gövdesine ekleyecektir.
Shape imgShape;

// Aşağıda, yerel dosya sistemindeki bir dosyadan görüntü almanın iki yolu bulunmaktadır.
// 1 - Bir görüntü dosyasından bir görüntü nesnesi oluşturun:
using (Image srcImage = Image.FromFile(ImageDir + "Logo.jpg"))
{
    imgShape = new Shape(doc, ShapeType.Image);
    doc.FirstSection.Body.FirstParagraph.AppendChild(imgShape);
    imgShape.ImageData.SetImage(srcImage);
}

// 2 - Bir akış kullanarak yerel dosya sisteminden bir görüntü dosyası açın:
using (Stream stream = new FileStream(ImageDir + "Logo.jpg", FileMode.Open, FileAccess.Read))
{
    imgShape = new Shape(doc, ShapeType.Image);
    doc.FirstSection.Body.FirstParagraph.AppendChild(imgShape);
    imgShape.ImageData.SetImage(stream);
    imgShape.Left = 150.0f;
}

doc.Save(ArtifactsDir + "Drawing.ImportImage.docx");
```

### Ayrıca bakınız

* class [ImageData](../)
* ad alanı [Aspose.Words.Drawing](../../imagedata/)
* toplantı [Aspose.Words](../../../)

---

## SetImage(string) {#setimage_2}

Şeklin gösterdiği görüntüyü ayarlar.

```csharp
public void SetImage(string fileName)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| fileName | String | Görüntü dosyası. Bir dosya adı veya URL olabilir. |

### Örnekler

Bir belgeye bağlantılı bir görüntünün nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string imageFileName = ImageDir + "Windows MetaFile.wmf";

// Aşağıda, bir şekli gösterebilmesi için bir şekle bir resim uygulamanın iki yolu verilmiştir.
// 1 - Resmi içerecek şekli ayarlayın.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SetImage(imageFileName);

builder.InsertNode(shape);

doc.Save(ArtifactsDir + "Image.CreateLinkedImage.Embedded.docx");

// Formda sakladığımız her resim belgemizin boyutunu artıracaktır.
Assert.True(70000 < new FileInfo(ArtifactsDir + "Image.CreateLinkedImage.Embedded.docx").Length);

doc.FirstSection.Body.FirstParagraph.RemoveAllChildren();

// 2 - Yerel dosya sistemindeki bir görüntü dosyasına bağlanacak şekli ayarlayın.
shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = imageFileName;

builder.InsertNode(shape);
doc.Save(ArtifactsDir + "Image.CreateLinkedImage.Linked.docx");

// Resimlere bağlantı vermek yerden tasarruf sağlar ve daha küçük bir belgeyle sonuçlanır.
// Ancak, belge yalnızca görüntüyü doğru olarak görüntüleyebilir.
// görüntü dosyası, şeklin "SourceFullName" özelliğinin işaret ettiği konumda bulunur.
Assert.True(10000 > new FileInfo(ArtifactsDir + "Image.CreateLinkedImage.Linked.docx").Length);
```

### Ayrıca bakınız

* class [ImageData](../)
* ad alanı [Aspose.Words.Drawing](../../imagedata/)
* toplantı [Aspose.Words](../../../)


