---
title: Field.GetFieldCode
second_title: Aspose.Words for .NET API Referansı
description: Field yöntem. Alan başlangıcı ile alan ayırıcı veya ayırıcı yoksa alan sonu arasındaki metni döndürür. Alt alanların hem alan kodu hem de alan sonucu dahil edilir.
type: docs
weight: 110
url: /tr/net/aspose.words.fields/field/getfieldcode/
---
## GetFieldCode() {#getfieldcode}

Alan başlangıcı ile alan ayırıcı (veya ayırıcı yoksa alan sonu) arasındaki metni döndürür. Alt alanların hem alan kodu hem de alan sonucu dahil edilir.

```csharp
public string GetFieldCode()
```

### Örnekler

Alan kodu kullanarak bir belgeye nasıl alan ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE \\@ \"dddd, MMMM dd, yyyy\"");

Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// InsertField yönteminin bu aşırı yüklemesi, eklenen alanları otomatik olarak günceller.
Assert.That(DateTime.Parse(field.Result), Is.EqualTo(DateTime.Today).Within(1).Days);
```

Bir alanın alan kodunun nasıl alınacağını gösterir.

```csharp
// IF alanı içinde MERGEFIELD içeren bir belge açın.
Document doc = new Document(MyDir + "Nested fields.docx");
FieldIf fieldIf = (FieldIf)doc.Range.Fields[0];

// Bir alanın alan kodunu almanın iki yolu vardır:
// 1 - İç alanlarını çıkar:
Assert.AreEqual(" IF  > 0 \" (surplus of ) \" \"\" ", fieldIf.GetFieldCode(false));

// 2 - İç alanlarını dahil et:
Assert.AreEqual($" IF \u0013 MERGEFIELD NetIncome \u0014\u0015 > 0 \" (surplus of \u0013 MERGEFIELD  NetIncome \\f $ \u0014\u0015) \" \"\" ",
    fieldIf.GetFieldCode(true));

// Varsayılan olarak GetFieldCode yöntemi iç alanları görüntüler.
Assert.AreEqual(fieldIf.GetFieldCode(), fieldIf.GetFieldCode(true));
```

### Ayrıca bakınız

* class [Field](../)
* ad alanı [Aspose.Words.Fields](../../field/)
* toplantı [Aspose.Words](../../../)

---

## GetFieldCode(bool) {#getfieldcode_1}

Alan başlangıcı ile alan ayırıcı (veya ayırıcı yoksa alan sonu) arasındaki metni döndürür.

```csharp
public string GetFieldCode(bool includeChildFieldCodes)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| includeChildFieldCodes | Boolean | `Doğru` alt alan kodlarının dahil edilmesi gerekiyorsa. |

### Örnekler

Bir alanın alan kodunun nasıl alınacağını gösterir.

```csharp
// IF alanı içinde MERGEFIELD içeren bir belge açın.
Document doc = new Document(MyDir + "Nested fields.docx");
FieldIf fieldIf = (FieldIf)doc.Range.Fields[0];

// Bir alanın alan kodunu almanın iki yolu vardır:
// 1 - İç alanlarını çıkar:
Assert.AreEqual(" IF  > 0 \" (surplus of ) \" \"\" ", fieldIf.GetFieldCode(false));

// 2 - İç alanlarını dahil et:
Assert.AreEqual($" IF \u0013 MERGEFIELD NetIncome \u0014\u0015 > 0 \" (surplus of \u0013 MERGEFIELD  NetIncome \\f $ \u0014\u0015) \" \"\" ",
    fieldIf.GetFieldCode(true));

// Varsayılan olarak GetFieldCode yöntemi iç alanları görüntüler.
Assert.AreEqual(fieldIf.GetFieldCode(), fieldIf.GetFieldCode(true));
```

### Ayrıca bakınız

* class [Field](../)
* ad alanı [Aspose.Words.Fields](../../field/)
* toplantı [Aspose.Words](../../../)


