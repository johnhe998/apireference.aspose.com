---
title: ShapeBase.AspectRatioLocked
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. Şeklin en boy oranının kilitli olup olmadığını belirtir.
type: docs
weight: 40
url: /tr/net/aspose.words.drawing/shapebase/aspectratiolocked/
---
## ShapeBase.AspectRatioLocked property

Şeklin en boy oranının kilitli olup olmadığını belirtir.

```csharp
public bool AspectRatioLocked { get; set; }
```

### Notlar

Varsayılan değer,[`ShapeType`](../shapetype/) , ShapeType.Image için **doğru** ancak diğer şekil türleri için **yanlış**.

Yalnızca üst düzey şekiller için etkiye sahiptir.

### Örnekler

Bir şeklin en boy oranının nasıl kilitleneceğini/kilidinin açılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir şekil ekle. Bu belgeyi Microsoft Word'de açarsak, ortaya çıkarmak için şekle sol tıklayabiliriz.
// Çevresini saran, boyutunu değiştirmek için tıklayıp sürükleyebileceğimiz sekiz boyutlandırma tutamacı.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

// Şeklin en boy oranını korumak için "AspectRatioLocked" özelliğini "true" olarak ayarlayın
// görüntünün hem yüksekliğini hem de genişliğini değiştiren dört çapraz boyutlandırma tutamacından herhangi birini kullanırken.
// Yüksekliği veya genişliği değiştiren herhangi bir ortogonal boyutlandırma tutamacının kullanılması, en boy oranını değiştirmeye devam edecektir.
// "AspectRatioLocked" özelliğini "false" olarak ayarlayarak
// tüm boyutlandırma tutamaçlarıyla görüntünün en boy oranını serbestçe değiştirin.
shape.AspectRatioLocked = lockAspectRatio;

doc.Save(ArtifactsDir + "Shape.AspectRatio.docx");
```

### Ayrıca bakınız

* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


