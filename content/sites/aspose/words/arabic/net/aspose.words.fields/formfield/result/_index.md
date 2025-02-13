---
title: FormField.Result
second_title: Aspose.Words لمراجع .NET API
description: FormField ملكية. الحصول على سلسلة تمثل نتيجة حقل النموذج هذا أو تعيينها.
type: docs
weight: 170
url: /ar/net/aspose.words.fields/formfield/result/
---
## FormField.Result property

الحصول على سلسلة تمثل نتيجة حقل النموذج هذا أو تعيينها.

```csharp
public string Result { get; set; }
```

### ملاحظات

بالنسبة لحقل نموذج نصي ، تكون النتيجة هي النص الموجود في الحقل.

بالنسبة لحقل نموذج مربع الاختيار ، يمكن أن تكون النتيجة "1" أو "0" للإشارة إلى التحديد أو عدم التحديد.

بالنسبة لحقل النموذج المنسدل ، تكون النتيجة هي السلسلة المحددة في القائمة المنسدلة.

ضبط`Result` لحقل نموذج نصي لا يطبق تنسيق النص المحدد في [`TextInputFormat`](../textinputformat/) . إذا كنت تريد تعيين قيمة وتطبيق تنسيق ، فاستخدم ملف[`SetTextInputValue`](../settextinputvalue/) طريقة.

للحصول على حقل نموذج نصي[`TextInputDefault`](../textinputdefault/) يتم تطبيق القيمة إذا*value* هو`لا شيء`.

### أمثلة

يوضح كيفية إدراج مربع تحرير وسرد.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// أدخل مربع تحرير وسرد يسمح للمستخدم باختيار خيار من مجموعة سلاسل.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

Assert.AreEqual("MyComboBox", comboBox.Name);
Assert.AreEqual(FieldType.FieldFormDropDown, comboBox.Type);
Assert.AreEqual("Apple", comboBox.Result);

// سيظهر حقل النموذج في شكل علامة html "تحديد".
doc.Save(ArtifactsDir + "FormFields.Create.html");
```

### أنظر أيضا

* class [FormField](../)
* مساحة الاسم [Aspose.Words.Fields](../../formfield/)
* المجسم [Aspose.Words](../../../)


