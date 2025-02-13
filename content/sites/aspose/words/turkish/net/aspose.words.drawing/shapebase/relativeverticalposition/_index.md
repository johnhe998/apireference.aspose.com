---
title: ShapeBase.RelativeVerticalPosition
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. Şeklin dikey olarak neye göre konumlandırıldığını belirtir.
type: docs
weight: 410
url: /tr/net/aspose.words.drawing/shapebase/relativeverticalposition/
---
## ShapeBase.RelativeVerticalPosition property

Şeklin dikey olarak neye göre konumlandırıldığını belirtir.

```csharp
public RelativeVerticalPosition RelativeVerticalPosition { get; set; }
```

### Notlar

Varsayılan değerParagraph.

Yalnızca üst düzey kayan şekiller için etkilidir.

### Örnekler

Bir sayfanın ortasına kayan bir görüntünün nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Üst üste binen metnin arkasında görünecek kayan bir resim ekleyin ve onu sayfanın ortasına hizalayın.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Ayrıca bakınız

* enum [RelativeVerticalPosition](../../relativeverticalposition/)
* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


