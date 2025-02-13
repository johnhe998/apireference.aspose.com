---
title: FieldOptions.FieldUpdateCultureSource
second_title: Aspose.Words لمراجع .NET API
description: FieldOptions ملكية. تحدد الثقافة المراد استخدامها لتنسيق نتيجة الحقل.
type: docs
weight: 100
url: /ar/net/aspose.words.fields/fieldoptions/fieldupdateculturesource/
---
## FieldOptions.FieldUpdateCultureSource property

تحدد الثقافة المراد استخدامها لتنسيق نتيجة الحقل.

```csharp
public FieldUpdateCultureSource FieldUpdateCultureSource { get; set; }
```

### ملاحظات

بشكل افتراضي ، يتم استخدام ثقافة الخيط الحالي.

يؤثر الإعداد فقط على حقول التاريخ / الوقت التي تحتوي على مفتاح تنسيق \\ @.

### أمثلة

يوضح كيفية تحديد مصدر الثقافة المستخدمة لتنسيق التاريخ أثناء تحديث الحقل أو دمج البريد.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل حقلي دمج باستخدام اللغة الألمانية.
builder.Font.LocaleId = new CultureInfo("de-DE").LCID;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

// اضبط الثقافة الحالية على اللغة الإنجليزية الأمريكية بعد الاحتفاظ بقيمتها الأصلية في متغير.
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");

// سيستخدم هذا الدمج ثقافة مؤشر الترابط الحالي لتنسيق التاريخ ، باللغة الإنجليزية الأمريكية.
doc.MailMerge.Execute(new[] { "Date1" }, new object[] { new DateTime(2020, 1, 01) });

// تكوين الدمج التالي للحصول على قيمة ثقافته من رمز الحقل. قيمة هذه الثقافة ستكون ألمانية.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.MailMerge.Execute(new[] { "Date2" }, new object[] { new DateTime(2020, 1, 01) });

// تحتوي نتيجة الدمج الأولى على تاريخ تم تنسيقه باللغة الإنجليزية ، بينما تحتوي النتيجة الثانية على تاريخ باللغة الألمانية.
Assert.AreEqual("Wednesday, 1 January 2020 - Mittwoch, 1 Januar 2020", doc.Range.Text.Trim());

// استعادة الثقافة الأصلية للخيط.
Thread.CurrentThread.CurrentCulture = currentCulture;
```

### أنظر أيضا

* enum [FieldUpdateCultureSource](../../fieldupdateculturesource/)
* class [FieldOptions](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldoptions/)
* المجسم [Aspose.Words](../../../)


