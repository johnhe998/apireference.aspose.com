---
title: FieldChar.GetField
second_title: Aspose.Words لمراجع .NET API
description: FieldChar طريقة. إرجاع حقل للحقل char .
type: docs
weight: 40
url: /ar/net/aspose.words.fields/fieldchar/getfield/
---
## FieldChar.GetField method

إرجاع حقل للحقل char .

```csharp
public Field GetField()
```

### قيمة الإرجاع

حقل لشار الحقل.

### ملاحظات

جديد[`Field`](../../field/) يتم إنشاء الكائن في كل مرة يتم استدعاء الطريقة.

### أمثلة

يوضح كيفية العمل مع عقدة FieldStart.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.Format.DateTimeFormat = "dddd, MMMM dd, yyyy";
field.Update();

FieldChar fieldStart = field.Start;

Assert.AreEqual(FieldType.FieldDate, fieldStart.FieldType);
Assert.AreEqual(false, fieldStart.IsDirty);
Assert.AreEqual(false, fieldStart.IsLocked);

// استرجع كائن الواجهة الذي يمثل الحقل في المستند.
field = (FieldDate)fieldStart.GetField();

Assert.AreEqual(false, field.IsLocked);
Assert.AreEqual(" DATE  \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// تحديث الحقل لإظهار التاريخ الحالي.
field.Update();
```

### أنظر أيضا

* class [Field](../../field/)
* class [FieldChar](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldchar/)
* المجسم [Aspose.Words](../../../)


