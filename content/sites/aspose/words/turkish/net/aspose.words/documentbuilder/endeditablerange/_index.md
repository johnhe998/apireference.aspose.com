---
title: DocumentBuilder.EndEditableRange
second_title: Aspose.Words for .NET API Referansı
description: DocumentBuilder yöntem. Belgedeki geçerli konumu düzenlenebilir bir aralık sonu olarak işaretler.
type: docs
weight: 210
url: /tr/net/aspose.words/documentbuilder/endeditablerange/
---
## EndEditableRange() {#endeditablerange}

Belgedeki geçerli konumu düzenlenebilir bir aralık sonu olarak işaretler.

```csharp
public EditableRangeEnd EndEditableRange()
```

### Geri dönüş değeri

Yeni oluşturulan düzenlenebilir aralık bitiş düğümü.

### Notlar

Bir belgedeki düzenlenebilir aralık, herhangi bir aralıkla örtüşebilir ve yayılabilir. Geçerli bir düzenlenebilir aralık oluşturmak için her ikisini de aramanız gerekir[`StartEditableRange`](../starteditablerange/) ve`EndEditableRange` veya`EndEditableRange`yöntemler.

Kötü biçimlendirilmiş düzenlenebilir aralık, belge kaydedildiğinde yok sayılır.

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

* class [EditableRangeEnd](../../editablerangeend/)
* class [DocumentBuilder](../)
* ad alanı [Aspose.Words](../../documentbuilder/)
* toplantı [Aspose.Words](../../../)

---

## EndEditableRange(EditableRangeStart) {#endeditablerange_1}

Belgedeki geçerli konumu düzenlenebilir bir aralık sonu olarak işaretler.

```csharp
public EditableRangeEnd EndEditableRange(EditableRangeStart start)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| start | EditableRangeStart | Bu düzenlenebilir aralık başlar. |

### Geri dönüş değeri

Yeni oluşturulan düzenlenebilir aralık bitiş düğümü.

### Notlar

Bu aşırı yüklemeyi iç içe düzenlenebilir aralıklar oluştururken kullanın.

Bir belgedeki düzenlenebilir aralık, herhangi bir aralıkla örtüşebilir ve yayılabilir. Geçerli bir düzenlenebilir aralık oluşturmak için her ikisini de aramanız gerekir[`StartEditableRange`](../starteditablerange/) ve`EndEditableRange` veya`EndEditableRange`yöntemler.

Kötü biçimlendirilmiş düzenlenebilir aralık, belge kaydedildiğinde yok sayılır.

### Örnekler

İç içe düzenlenebilir aralıkların nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "MyPassword");

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " +
                "we cannot edit this paragraph without the password.");

// İç içe iki düzenlenebilir aralık oluşturun.
EditableRangeStart outerEditableRangeStart = builder.StartEditableRange();
builder.Writeln("This paragraph inside the outer editable range and can be edited.");

EditableRangeStart innerEditableRangeStart = builder.StartEditableRange();
builder.Writeln("This paragraph inside both the outer and inner editable ranges and can be edited.");

// Şu anda, belge oluşturucunun düğüm ekleme imleci, devam eden birden fazla düzenlenebilir aralıkta.
// Bu durumda düzenlenebilir bir aralığı sonlandırmak istediğimizde,
// EditableRangeStart düğümünü geçerek hangi aralıkları bitirmek istediğimizi belirtmemiz gerekiyor.
builder.EndEditableRange(innerEditableRangeStart);

builder.Writeln("This paragraph inside the outer editable range and can be edited.");

builder.EndEditableRange(outerEditableRangeStart);

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

// Bir metin bölgesinde, belirtilen gruplarla çakışan iki düzenlenebilir aralık varsa,
// her iki grup tarafından hariç tutulan birleştirilmiş kullanıcı grubunun onu düzenlemesi engellenir.
outerEditableRangeStart.EditableRange.EditorGroup = EditorType.Everyone;
innerEditableRangeStart.EditableRange.EditorGroup = EditorType.Contributors;

doc.Save(ArtifactsDir + "EditableRange.Nested.docx");
```

### Ayrıca bakınız

* class [EditableRangeEnd](../../editablerangeend/)
* class [EditableRangeStart](../../editablerangestart/)
* class [DocumentBuilder](../)
* ad alanı [Aspose.Words](../../documentbuilder/)
* toplantı [Aspose.Words](../../../)


