---
title: PdfSaveOptions.Clone
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions طريقة. لإنشاء نسخة عميقة من هذا الكائن .
type: docs
weight: 310
url: /ar/net/aspose.words.saving/pdfsaveoptions/clone/
---
## PdfSaveOptions.Clone method

لإنشاء نسخة عميقة من هذا الكائن .

```csharp
public PdfSaveOptions Clone()
```

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

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


