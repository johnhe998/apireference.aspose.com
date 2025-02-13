---
title: PdfSaveOptions.PreblendImages
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم المزج المسبق للصور الشفافة بلون خلفية أسود أم لا.
type: docs
weight: 230
url: /ar/net/aspose.words.saving/pdfsaveoptions/preblendimages/
---
## PdfSaveOptions.PreblendImages property

الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم المزج المسبق للصور الشفافة بلون خلفية أسود أم لا.

```csharp
public bool PreblendImages { get; set; }
```

### ملاحظات

قد يؤدي دمج الصور مسبقًا إلى تحسين المظهر المرئي لوثيقة PDF في Adobe Reader وإزالة عيوب الصقل.

من أجل عرض الصور الممزوجة مسبقًا بشكل صحيح ، يجب أن يدعم تطبيق عارض PDF / غير اللامع في قاموس الصور ذات القناع الناعم.

النظام الأساسي`خاطئة`.

### أمثلة

يوضح كيفية مزج الصور مسبقًا بخلفيات شفافة أثناء حفظ مستند في PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Image img = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.InsertImage(img);

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// اضبط خاصية "PreblendImages" على "true" لمزج الصور الشفافة مسبقًا
// مع خلفية ، مما قد يقلل من القطع الأثرية.
// اضبط خاصية "PreblendImages" على "false" لعرض الصور الشفافة بشكل طبيعي.
options.PreblendImages = preblendImages;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreblendImages.pdf", options);
```

يوضح كيفية المزج المسبق للصور بخلفيات شفافة (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (Image image = Image.Decode(ImageDir + "Transparent background logo.png"))
    builder.InsertImage(image);

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// اضبط خاصية "PreblendImages" على "true" لمزج الصور الشفافة مسبقًا
// مع خلفية ، مما قد يقلل من القطع الأثرية.
// اضبط خاصية "PreblendImages" على "false" لعرض الصور الشفافة بشكل طبيعي.
options.PreblendImages = preblendImages;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreblendImagesNetStandard2.pdf", options);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


