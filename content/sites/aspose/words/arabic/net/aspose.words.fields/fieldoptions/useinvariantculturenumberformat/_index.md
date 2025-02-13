---
title: FieldOptions.UseInvariantCultureNumberFormat
second_title: Aspose.Words لمراجع .NET API
description: FieldOptions ملكية. الحصول على أو تعيين القيمة التي تشير إلى أن تنسيق الأرقام يتم تحليله باستخدام ثقافة ثابتة أو لا
type: docs
weight: 190
url: /ar/net/aspose.words.fields/fieldoptions/useinvariantculturenumberformat/
---
## FieldOptions.UseInvariantCultureNumberFormat property

الحصول على أو تعيين القيمة التي تشير إلى أن تنسيق الأرقام يتم تحليله باستخدام ثقافة ثابتة أو لا

```csharp
public bool UseInvariantCultureNumberFormat { get; set; }
```

### ملاحظات

عندما يتم تعيين هذه الخاصية على **حقيقي** ، تنسيق الأرقام مأخوذ من ثقافة ثابتة.

عندما يتم تعيين هذه الخاصية على **خاطئة**، تنسيق الأرقام مأخوذ من ثقافة الموضوع الحالي.

النظام الأساسي **خاطئة**.

### أمثلة

يوضح كيفية تنسيق الأرقام وفقًا للثقافة الثابتة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
Field field = builder.InsertField(" = 1234567,89 \\# $#,###,###.##");
field.Update();

// في بعض الأحيان ، قد لا تقوم الحقول بتنسيق أرقامها بشكل صحيح في ظل ثقافات معينة. 
Assert.IsFalse(doc.FieldOptions.UseInvariantCultureNumberFormat);
Assert.AreEqual("$1234567,89 .     ", field.Result);

// لإصلاح ذلك ، يمكننا تغيير ثقافة الموضوع بأكمله.
// هناك طريقة أخرى لإصلاح ذلك وهي تعيين هذه العلامة ،
// الذي يجعل جميع الحقول تستخدم الثقافة الثابتة عند تنسيق الأرقام.
// تسمح لنا هذه الطريقة بتجنب تغيير ثقافة الموضوع بأكمله.
doc.FieldOptions.UseInvariantCultureNumberFormat = true;
field.Update();
Assert.AreEqual("$1.234.567,89", field.Result);
```

### أنظر أيضا

* class [FieldOptions](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldoptions/)
* المجسم [Aspose.Words](../../../)


