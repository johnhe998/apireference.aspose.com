---
title: EditableRange.Id
second_title: Aspose.Words for .NET API Referansı
description: EditableRange mülk. Düzenlenebilir aralık tanımlayıcısını alır.
type: docs
weight: 40
url: /tr/net/aspose.words/editablerange/id/
---
## EditableRange.Id property

Düzenlenebilir aralık tanımlayıcısını alır.

```csharp
public int Id { get; }
```

### Notlar

Bölge, kullanılarak sınırlandırılmalıdır.[`EditableRangeStart`](../editablerangestart/) ve[`EditableRangeEnd`](../editablerangeend/)

Düzenlenebilir aralık tanımlayıcılarının bir belge genelinde benzersiz olması gerekir ve Aspose.Words otomatik olarak belgeleri yüklerken, kaydederken ve birleştirirken düzenlenebilir aralık tanımlayıcılarını korur.

### Örnekler

Düzenlenebilir bir aralıkla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "MyPassword");

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! Since we have set the document's protection level to read-only," +
                " we cannot edit this paragraph without the password.");

// Düzenlenebilir aralıklar, korunan belgelerin bölümlerini düzenleme için açık bırakmamıza izin verir.
EditableRangeStart editableRangeStart = builder.StartEditableRange();
builder.Writeln("This paragraph is inside an editable range, and can be edited.");
EditableRangeEnd editableRangeEnd = builder.EndEditableRange();

// İyi biçimlendirilmiş bir düzenlenebilir aralığın bir başlangıç düğümü ve bir bitiş düğümü vardır.
// Bu düğümlerin eşleşen kimlikleri vardır ve düzenlenebilir düğümleri kapsar.
EditableRange editableRange = editableRangeStart.EditableRange;

Assert.AreEqual(editableRangeStart.Id, editableRange.Id);
Assert.AreEqual(editableRangeEnd.Id, editableRange.Id);

// Düzenlenebilir aralığın farklı bölümleri birbirine bağlanır.
Assert.AreEqual(editableRangeStart.Id, editableRange.EditableRangeStart.Id);
Assert.AreEqual(editableRangeStart.Id, editableRangeEnd.EditableRangeStart.Id);
Assert.AreEqual(editableRange.Id, editableRangeStart.EditableRange.Id);
Assert.AreEqual(editableRangeEnd.Id, editableRange.EditableRangeEnd.Id);

// Her parçanın düğüm tiplerine bu şekilde ulaşabiliriz. Düzenlenebilir aralığın kendisi bir düğüm değil,
// ancak bir başlangıç, bir son ve bunların kapalı içeriklerinden oluşan bir varlık.
Assert.AreEqual(NodeType.EditableRangeStart, editableRangeStart.NodeType);
Assert.AreEqual(NodeType.EditableRangeEnd, editableRangeEnd.NodeType);

builder.Writeln("This paragraph is outside the editable range, and cannot be edited.");

doc.Save(ArtifactsDir + "EditableRange.CreateAndRemove.docx");

// Düzenlenebilir bir aralığı kaldırın. Aralık içindeki tüm düğümler bozulmadan kalacaktır.
editableRange.Remove();
```

### Ayrıca bakınız

* class [EditableRange](../)
* ad alanı [Aspose.Words](../../editablerange/)
* toplantı [Aspose.Words](../../../)


