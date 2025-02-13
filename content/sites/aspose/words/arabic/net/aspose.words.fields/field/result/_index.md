---
title: Field.Result
second_title: Aspose.Words لمراجع .NET API
description: Field ملكية. الحصول على أو تعيين النص الموجود بين فاصل الحقل ونهاية الحقل.
type: docs
weight: 70
url: /ar/net/aspose.words.fields/field/result/
---
## Field.Result property

الحصول على أو تعيين النص الموجود بين فاصل الحقل ونهاية الحقل.

```csharp
public string Result { get; set; }
```

### أمثلة

يوضح كيفية إدراج حقل في مستند باستخدام رمز حقل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE \\@ \"dddd, MMMM dd, yyyy\"");

Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// هذا التحميل الزائد لطريقة InsertField يقوم تلقائيًا بتحديث الحقول المدرجة.
Assert.That(DateTime.Parse(field.Result), Is.EqualTo(DateTime.Today).Within(1).Days);
```

### أنظر أيضا

* class [Field](../)
* مساحة الاسم [Aspose.Words.Fields](../../field/)
* المجسم [Aspose.Words](../../../)


