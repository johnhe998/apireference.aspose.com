---
title: DocumentBuilder.MoveToField
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. ينقل المؤشر إلى حقل في المستند.
type: docs
weight: 510
url: /ar/net/aspose.words/documentbuilder/movetofield/
---
## DocumentBuilder.MoveToField method

ينقل المؤشر إلى حقل في المستند.

```csharp
public void MoveToField(Field field, bool isAfter)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| field | Field | الحقل المراد تحريك المؤشر إليه. |
| isAfter | Boolean | عندما يكون صحيحًا ، ينقل المؤشر ليكون بعد نهاية الحقل . عندما يكون خطأ ، ينقل المؤشر ليكون قبل بدء الحقل. |

### أمثلة

يوضح كيفية نقل مؤشر نقطة إدراج عقدة منشئ المستندات إلى حقل معين.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل حقلاً باستخدام DocumentBuilder وأضف سلسلة نصية بعده.
Field field = builder.InsertField(" AUTHOR \"John Doe\" ");

// مؤشر الباني موجود حاليًا في نهاية المستند.
Assert.Null(builder.CurrentNode);

// حرك المؤشر إلى الحقل أثناء تحديد ما إذا كان سيتم وضع هذا المؤشر قبل الحقل أو بعده.
builder.MoveToField(field, moveCursorToAfterTheField);

// لاحظ أن المؤشر خارج الحقل في كلتا الحالتين.
// هذا يعني أنه لا يمكننا تحرير الحقل باستخدام المنشئ مثل هذا.
// لتحرير حقل ، يمكننا استخدام طريقة MoveTo للباني في FieldStart للحقل
// أو عقدة FieldSeparator لوضع المؤشر بالداخل.
if (moveCursorToAfterTheField)
{
    Assert.Null(builder.CurrentNode);
    builder.Write(" Text immediately after the field.");

    Assert.AreEqual("\u0013 AUTHOR \"John Doe\" \u0014John Doe\u0015 Text immediately after the field.", 
        doc.GetText().Trim());
}
else
{
    Assert.AreEqual(field.Start, builder.CurrentNode);
    builder.Write("Text immediately before the field. ");

    Assert.AreEqual("Text immediately before the field. \u0013 AUTHOR \"John Doe\" \u0014John Doe\u0015", 
        doc.GetText().Trim());
}
```

### أنظر أيضا

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


