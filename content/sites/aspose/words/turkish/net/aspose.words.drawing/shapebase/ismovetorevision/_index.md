---
title: ShapeBase.IsMoveToRevision
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. İade doğru bu nesne değişiklik izleme etkinken Microsoft Wordde taşındıysa yerleştirildiyse.
type: docs
weight: 320
url: /tr/net/aspose.words.drawing/shapebase/ismovetorevision/
---
## ShapeBase.IsMoveToRevision property

İade **doğru** bu nesne, değişiklik izleme etkinken Microsoft Word'de taşındıysa (yerleştirildiyse).

```csharp
public bool IsMoveToRevision { get; }
```

### Örnekler

Hareket revizyon şekillerinin nasıl tanımlanacağını gösterir.

```csharp
// Taşıma revizyonu, belge gövdesindeki bir öğeyi Microsoft Word'de kesip yapıştırarak taşıdığımız zamandır.
// değişiklikleri izleme. Böyle bir metin hareketine satır içi bir şekil katarsak, o şekil de bir revizyon olacaktır.
// Kopyalama ve yapıştırma veya hareketli kayan şekiller, taşıma revizyonları oluşturmaz.
Document doc = new Document(MyDir + "Revision shape.docx");

// Revizyonları taşıma, "Taşı" ve "Taşı" revizyonlarından oluşur. Bu belgede tek bir şekilde hareket ettik,
// ancak biz taşıma revizyonunu kabul edene veya reddedene kadar, bu şeklin iki örneği olacaktır.
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// Bu, varış hedefindeki şekil olan "Taşı" revizyonudur.
// Revizyonu kabul edersek, bu "Taşı" revizyon şekli kaybolacaktır,
// ve "Taşı" revizyon şekli kalacaktır.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Bu, orijinal konumunda şekil olan "Taşı" revizyonudur.
// Revizyonu kabul edersek, bu "Taşı" revizyon şekli kaybolacak,
// ve "Taşı" revizyon şekli kalacaktır.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

### Ayrıca bakınız

* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


