---
title: resim
linktitle: resim
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET Adım adım kılavuz ile görüntü eklemeyi ve özelleştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/image/
---

Bu örnekte görüntü özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını açıklayacağız. Resimler, bir belgeye çizimler ve grafikler eklemenizi sağlar.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Resim ekleme

 kullanarak bir resim ekleyebiliriz.`Shape` sınıfı ve görüntünün türünü belirtmek, burada`ShapeType.Image` . Ayrıca görüntünün kaydırma türünü de ayarladık.`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 3. Adım: Görüntü Özelleştirme

 Resmi tam yolunu belirterek özelleştiriyoruz, örneğin`"/attachment/1456/pic001.png"`ve görüntüye bir başlık ekleme.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Aspose.Words for .NET ile görseller için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Resim ekle.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Tebrikler! Artık resimler özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.


### SSS

#### S: Yerel bir dosyadan Aspose.Words'e nasıl resim ekleyebilirim?

 C: Yerel bir dosyadan Aspose.Words'e bir görüntü eklemek için`Shape` sınıf ve`InsertImage` yöntem.

#### S: Aspose.Words'te bir URL'den resim ekleyebilir miyim?

 C: Evet, Aspose.Words'te bir URL'den resim ekleyebilirsiniz. aynısını kullanabilirsin`InsertImage`yöntemini seçin ve yerel dosya yolu yerine resim URL'sini belirtin.

#### S: Aspose.Words'te bir görüntüyü nasıl yeniden boyutlandırabilirim?

 C: Aspose.Words'te bir görüntüyü yeniden boyutlandırmak için`Width` Ve`Height` özellikleri`Shape` nesne.

#### S: Aspose.Words'ta resimlere filtre uygulayabilir miyim?

 C: Evet, Aspose.Words'ta resimlere filtre uygulayabilirsiniz. Örneğin, bir görüntüye bulanıklık filtresi uygulayabilirsiniz.`ApplyGaussianBlur` yöntemi`Shape` nesne.

#### S: Aspose.Words'te bir görüntüyü diğeriyle nasıl değiştirebilirim?

 C: Aspose.Words'te bir görüntüyü diğeriyle değiştirmek için`Replace` yöntemi`Shape` sınıf. Bu yöntem parametre olarak alır`Shape` değiştirilecek görüntünün nesnesi ve`Shape` yeni görüntünün nesnesi.