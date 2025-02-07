---
title: Field.IsLocked
second_title: Aspose.Words لمراجع .NET API
description: Field ملكية. تحديد ما إذا كان الحقل مغلقًا أم لا يجب عدم إعادة حساب النتيجة.
type: docs
weight: 50
url: /ar/net/aspose.words.fields/field/islocked/
---
## Field.IsLocked property

تحديد ما إذا كان الحقل مغلقًا أم لا (يجب عدم إعادة حساب النتيجة).

```csharp
public bool IsLocked { get; set; }
```

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

* class [Field](../)
* مساحة الاسم [Aspose.Words.Fields](../../field/)
* المجسم [Aspose.Words](../../../)


