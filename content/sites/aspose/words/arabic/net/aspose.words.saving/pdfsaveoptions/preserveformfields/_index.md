---
title: PdfSaveOptions.PreserveFormFields
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. يحدد ما إذا كان سيتم الاحتفاظ بحقول نموذج Microsoft Word كحقول نموذج في PDF أو تحويلها إلى نص. الافتراضي هوخاطئة .
type: docs
weight: 240
url: /ar/net/aspose.words.saving/pdfsaveoptions/preserveformfields/
---
## PdfSaveOptions.PreserveFormFields property

يحدد ما إذا كان سيتم الاحتفاظ بحقول نموذج Microsoft Word كحقول نموذج في PDF أو تحويلها إلى نص. الافتراضي هو`خاطئة` .

```csharp
public bool PreserveFormFields { get; set; }
```

### ملاحظات

تتضمن حقول نموذج Microsoft Word إدخال نص وقائمة منسدلة وعناصر تحكم في مربعات الاختيار.

عند الضبط على`خاطئة` ، سيتم تصدير هذه الحقول كنص إلى PDF. عند الضبط على`حقيقي`، سيتم تصدير هذه الحقول كحقول نموذج PDF.

عند تصدير حقول النموذج إلى PDF كحقول نموذج ، فقد يحدث بعض فقدان التنسيق لأن حقول نموذج PDF لا تدعم جميع ميزات حقول نموذج Microsoft Word.

يعتمد حجم المخرجات أيضًا على حجم المحتوى لأن النماذج القابلة للتحرير في Microsoft Word هي كائنات مضمنة.

النماذج القابلة للتحرير محظورة بموجب التوافق مع PDF / A.`خاطئة` سيتم استخدام القيمة تلقائيًا عند الحفظ في PDF / A.

لا يتم دعم حقول النموذج عند الحفظ في PDF / UA.`خاطئة` سيتم استخدام القيمة تلقائيًا.

### أمثلة

يوضح كيفية حفظ مستند بتنسيق PDF باستخدام طريقة Save وفئة PdfSaveOptions.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// أدخل مربع تحرير وسرد يسمح للمستخدم باختيار خيار من مجموعة سلاسل.
builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions pdfOptions = new PdfSaveOptions();

// اضبط خاصية "PreserveFormFields" على "true" لحفظ حقول النموذج ككائنات تفاعلية في ملف PDF الناتج.
// اضبط خاصية "PreserveFormFields" على "false" لتجميد كافة حقول النموذج في المستند في
// قيمها الحالية وعرضها كنص عادي في ملف PDF الناتج.
pdfOptions.PreserveFormFields = preserveFormFields;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreserveFormFields.pdf", pdfOptions);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


