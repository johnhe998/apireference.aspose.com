---
title: FieldOptions.PreProcessCulture
second_title: Aspose.Words لمراجع .NET API
description: FieldOptions ملكية. الحصول على الثقافة أو تعيينها لقيم حقل المعالجة المسبقة.
type: docs
weight: 150
url: /ar/net/aspose.words.fields/fieldoptions/preprocessculture/
---
## FieldOptions.PreProcessCulture property

الحصول على الثقافة أو تعيينها لقيم حقل المعالجة المسبقة.

```csharp
public CultureInfo PreProcessCulture { get; set; }
```

### ملاحظات

لا تؤثر هذه الخاصية حاليًا إلا على قيمة[`FieldDocProperty`](../../fielddocproperty/) مجال.

النظام الأساسي **لا شيء** . عندما يتم تعيين هذه الخاصية على **لا شيء** ، ال[`FieldDocProperty`](../../fielddocproperty/) قيمة الحقل مُجهزة مسبقًا مع الثقافة التي يتحكم فيها[`FieldUpdateCultureSource`](../fieldupdateculturesource/) منشأه.

### أمثلة

يوضح كيفية ضبط ثقافة المعالجة المسبقة.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بتعيين الثقافة التي ستنسق بعض الحقول وفقًا لها القيم المعروضة.
doc.FieldOptions.PreProcessCulture = new CultureInfo("de-DE");

Field field = builder.InsertField(" DOCPROPERTY CreateTime");

// سيعرض حقل DOCPROPERTY نتيجة منسقة وفقًا لثقافة المعالجة المسبقة
// لقد حددنا اللغة الألمانية. سيعرض الحقل التاريخ / الوقت باستخدام تنسيق "dd.mm.yyyy hh: mm".
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[.]\d{2}[.]\d{4} \d{2}[:]\d{2}").Success);

doc.FieldOptions.PreProcessCulture = CultureInfo.InvariantCulture;
field.Update();

// بعد التبديل إلى الثقافة الثابتة ، سيستخدم حقل DOCPROPERTY تنسيق "mm / dd / yyyy hh: mm".
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[/]\d{2}[/]\d{4} \d{2}[:]\d{2}").Success);
```

### أنظر أيضا

* class [FieldOptions](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldoptions/)
* المجسم [Aspose.Words](../../../)


