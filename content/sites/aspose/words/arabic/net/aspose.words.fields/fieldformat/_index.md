---
title: Class FieldFormat
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fields.FieldFormat فصل. يوفر وصولاً مكتوبًا إلى التنسيق الرقمي والتاريخ والوقت والحقل العام.
type: docs
weight: 1790
url: /ar/net/aspose.words.fields/fieldformat/
---
## FieldFormat class

يوفر وصولاً مكتوبًا إلى التنسيق الرقمي والتاريخ والوقت والحقل العام.

```csharp
public class FieldFormat
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [DateTimeFormat](../../aspose.words.fields/fieldformat/datetimeformat/) { get; set; } | الحصول على تنسيق يتم تطبيقه على نتيجة حقل التاريخ والوقت أو تعيينه. يتوافق مع \ @ switch. |
| [GeneralFormats](../../aspose.words.fields/fieldformat/generalformats/) { get; } | الحصول على مجموعة من التنسيقات العامة التي يتم تطبيقها على نتيجة رقمية أو نصية أو أي حقل. |
| [NumericFormat](../../aspose.words.fields/fieldformat/numericformat/) { get; set; } | الحصول على تنسيق يتم تطبيقه على نتيجة حقل رقمية أو تعيينه. يتوافق مع \ # switch. |

### أمثلة

يوضح كيفية تنسيق النتائج الميدانية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// استخدم منشئ المستندات لإدراج حقل يعرض نتيجة بدون أي تنسيق مطبق.
Field field = builder.InsertField("= 2 + 3");

Assert.AreEqual("= 2 + 3", field.GetFieldCode());
Assert.AreEqual("5", field.Result);

// يمكننا تطبيق تنسيق على نتيجة الحقل باستخدام خصائص الحقل.
// فيما يلي ثلاثة أنواع من التنسيقات التي يمكننا تطبيقها على نتيجة الحقل.
// 1 - التنسيق الرقمي:
FieldFormat format = field.Format;
format.NumericFormat = "$###.00";
field.Update();

Assert.AreEqual("= 2 + 3 \\# $###.00", field.GetFieldCode());
Assert.AreEqual("$  5.00", field.Result);

// 2 - تنسيق التاريخ / الوقت:
field = builder.InsertField("DATE");
format = field.Format;
format.DateTimeFormat = "dddd, MMMM dd, yyyy";
field.Update();

Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());
Console.WriteLine($"Today's date, in {format.DateTimeFormat} format:\n\t{field.Result}");

// 3 - التنسيق العام:
field = builder.InsertField("= 25 + 33");
format = field.Format;
format.GeneralFormats.Add(GeneralFormat.LowercaseRoman);
format.GeneralFormats.Add(GeneralFormat.Upper);
field.Update();

int index = 0;
using (IEnumerator<GeneralFormat> generalFormatEnumerator = format.GeneralFormats.GetEnumerator())
    while (generalFormatEnumerator.MoveNext())
        Console.WriteLine($"General format index {index++}: {generalFormatEnumerator.Current}");

Assert.AreEqual("= 25 + 33 \\* roman \\* Upper", field.GetFieldCode());
Assert.AreEqual("LVIII", field.Result);
Assert.AreEqual(2, format.GeneralFormats.Count);
Assert.AreEqual(GeneralFormat.LowercaseRoman, format.GeneralFormats[0]);

// يمكننا إزالة التنسيقات الخاصة بنا لإعادة نتيجة الحقل إلى شكله الأصلي.
format.GeneralFormats.Remove(GeneralFormat.LowercaseRoman);
format.GeneralFormats.RemoveAt(0);
Assert.AreEqual(0, format.GeneralFormats.Count);
field.Update();

Assert.AreEqual("= 25 + 33  ", field.GetFieldCode());
Assert.AreEqual("58", field.Result);
Assert.AreEqual(0, format.GeneralFormats.Count);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Fields](../../aspose.words.fields/)
* المجسم [Aspose.Words](../../)


