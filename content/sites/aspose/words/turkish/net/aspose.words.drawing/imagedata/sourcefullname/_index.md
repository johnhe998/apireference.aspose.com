---
title: ImageData.SourceFullName
second_title: Aspose.Words for .NET API Referansı
description: ImageData mülk. Bağlantılı görüntü için kaynak dosyanın yolunu ve adını alır veya ayarlar.
type: docs
weight: 170
url: /tr/net/aspose.words.drawing/imagedata/sourcefullname/
---
## ImageData.SourceFullName property

Bağlantılı görüntü için kaynak dosyanın yolunu ve adını alır veya ayarlar.

```csharp
public string SourceFullName { get; set; }
```

### Notlar

Varsayılan değer boş bir dizedir.

Eğer`SourceFullName` boş bir dize değil, görüntü bağlantılı.

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


