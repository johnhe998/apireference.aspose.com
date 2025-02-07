---
title: SaveOptions.UpdateFields
second_title: Aspose.Words لمراجع .NET API
description: SaveOptions ملكية. الحصول على قيمة أو تعيينها لتحديد ما إذا كان يجب تحديث حقول من أنواع معينة قبل حفظ المستند بتنسيق صفحة ثابت . القيمة الافتراضية لهذه الخاصية هي حقيقي .
type: docs
weight: 170
url: /ar/net/aspose.words.saving/saveoptions/updatefields/
---
## SaveOptions.UpdateFields property

الحصول على قيمة أو تعيينها لتحديد ما إذا كان يجب تحديث حقول من أنواع معينة قبل حفظ المستند بتنسيق صفحة ثابت . القيمة الافتراضية لهذه الخاصية هي **حقيقي** .

```csharp
public bool UpdateFields { get; set; }
```

### ملاحظات

يسمح بتحديد ما إذا كان سيتم تقليد سلوك MS Word أم لا.

### أمثلة

يوضح كيفية تحديث كل الحقول في مستند على الفور قبل حفظه في PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل نصًا مع حقلي PAGE و NUMPAGES. لا تعرض هذه الحقول القيمة الصحيحة في الوقت الحقيقي.
// سنحتاج إلى تحديثها يدويًا باستخدام طرق التحديث مثل "Field.Update ()" و "Document.UpdateFields ()"
// في كل مرة نحتاجها لعرض قيم دقيقة.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Hello World!");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// اضبط خاصية "UpdateFields" على "false" لعدم تحديث كافة الحقول الموجودة في المستند مباشرة قبل عملية الحفظ.
// هذا هو الخيار المفضل إذا علمنا أن جميع حقولنا ستكون محدثة قبل الحفظ.
// اضبط خاصية "UpdateFields" على "true" للتكرار خلال كل المستندات
// الحقول وتحديثها قبل أن نحفظها كملف PDF. سيضمن هذا عرض جميع الحقول
// القيم الأكثر دقة في ملف PDF.
options.UpdateFields = updateFields;

// يمكننا استنساخ كائنات PdfSaveOptions.
Assert.AreNotSame(options, options.Clone());

doc.Save(ArtifactsDir + "PdfSaveOptions.UpdateFields.pdf", options);
```

### أنظر أيضا

* class [SaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../saveoptions/)
* المجسم [Aspose.Words](../../../)


