---
title: PdfSaveOptions.InterpolateImages
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. علامة تشير إلى ما إذا كان يجب إجراء استكمال الصورة بواسطة قارئ مطابق. متىخاطئة لم يتم تحديد العلامة إلى مستند الإخراج و يتم استخدام السلوك الافتراضي للقارئ بدلاً من ذلك.
type: docs
weight: 180
url: /ar/net/aspose.words.saving/pdfsaveoptions/interpolateimages/
---
## PdfSaveOptions.InterpolateImages property

علامة تشير إلى ما إذا كان يجب إجراء استكمال الصورة بواسطة قارئ مطابق. متى`خاطئة` لم يتم تحديد العلامة إلى مستند الإخراج و يتم استخدام السلوك الافتراضي للقارئ بدلاً من ذلك.

```csharp
public bool InterpolateImages { get; set; }
```

### ملاحظات

عندما تكون دقة الصورة المصدر أقل بكثير من دقة جهاز الإخراج ، تغطي كل عينة مصدر العديد من وحدات البكسل للجهاز. نتيجة لذلك ، يمكن أن تظهر الصور متعرجة أو ممتلئة . يمكن تقليل هذه الآثار المرئية عن طريق تطبيق خوارزمية إقحام الصورة أثناء العرض. الانتقال بين قيم العينة المجاورة.

قد يختار القارئ المطابق عدم تنفيذ هذه الميزة في ملف PDF ، أو قد يستخدم أي تنفيذ محدد للإقحام يرغب فيه.

النظام الأساسي`خاطئة`.

علامة الاستيفاء محظورة من خلال التوافق مع PDF / A.`خاطئة` سيتم استخدام القيمة تلقائيًا عند الحفظ في PDF / A.

### أمثلة

يوضح كيفية إجراء الإقحام على الصور أثناء حفظ مستند في PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Image img = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.InsertImage(img);

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// اضبط خاصية "InterpolateImages" على "true" لجعل القارئ الذي يفتح هذا المستند يقحم الصور.
// يجب أن تكون دقتها أقل من دقة الجهاز الذي يعرض المستند.
// اضبط خاصية "InterpolateImages" على "false" لجعلها بحيث لا يطبق القارئ أي استيفاء.
saveOptions.InterpolateImages = interpolateImages;

// عندما نفتح هذا المستند بقارئ مثل Adobe Acrobat ، سنحتاج إلى تكبير الصورة
// لرؤية تأثير الاستيفاء إذا قمنا بحفظ المستند مع تمكينه.
doc.Save(ArtifactsDir + "PdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

يوضح كيفية تحسين جودة الصورة في المستندات المقدمة (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (Image image = Image.Decode(ImageDir + "Transparent background logo.png"))
    builder.InsertImage(image);

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// اضبط خاصية "InterpolateImages" على "true" لجعل القارئ الذي يفتح هذا المستند يقحم الصور.
// يجب أن تكون دقتها أقل من دقة الجهاز الذي يعرض المستند.
// اضبط خاصية "InterpolateImages" على "false" لجعلها بحيث لا يطبق القارئ أي استيفاء.
saveOptions.InterpolateImages = interpolateImages;

// عندما نفتح هذا المستند بقارئ مثل Adobe Acrobat ، سنحتاج إلى تكبير الصورة
// لرؤية تأثير الاستيفاء إذا قمنا بحفظ المستند مع تمكينه.
doc.Save(ArtifactsDir + "PdfSaveOptions.InterpolateImagesNetStandard2.pdf", saveOptions);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


