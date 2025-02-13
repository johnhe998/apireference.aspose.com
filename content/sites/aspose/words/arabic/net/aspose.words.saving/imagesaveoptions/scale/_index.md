---
title: ImageSaveOptions.Scale
second_title: Aspose.Words لمراجع .NET API
description: ImageSaveOptions ملكية. الحصول على أو تحديد عامل التكبير / التصغير للصور التي تم إنشاؤها.
type: docs
weight: 140
url: /ar/net/aspose.words.saving/imagesaveoptions/scale/
---
## ImageSaveOptions.Scale property

الحصول على أو تحديد عامل التكبير / التصغير للصور التي تم إنشاؤها.

```csharp
public float Scale { get; set; }
```

### ملاحظات

القيمة الافتراضية هي 1.0. يجب أن تكون القيمة أكبر من 0.

### أمثلة

يوضح كيفية تحويل كائن Office Math إلى ملف صورة في نظام الملفات المحلي.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// قم بإنشاء كائن "ImageSaveOptions" لتمريره إلى طريقة "Save" لتعديل طريقة عرض العقدة
// كيف يعرض عقدة OfficeMath في صورة.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// اضبط خاصية "Scale" على 5 لجعل الكائن خمسة أضعاف حجمه الأصلي.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

يوضح كيفية تحرير الصورة بينما يقوم Aspose.Words بتحويل مستند إلى واحد.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// عندما نحفظ المستند كصورة ، يمكننا تمرير كائن SaveOptions إليه
// تحرير الصورة بينما تعرضها عملية الحفظ.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png)
{
    // يمكننا ضبط هذه الخصائص لتغيير سطوع الصورة وتباينها.
    // كلاهما على مقياس 0-1 وهما 0.5 افتراضيًا.
    ImageBrightness = 0.3f,
    ImageContrast = 0.7f,

    // يمكننا ضبط الدقة الأفقية والعمودية بهذه الخصائص.
    // سيؤثر هذا على أبعاد الصورة.
    // القيمة الافتراضية لهذه الخصائص هي 96.0 ، لدقة 96 نقطة في البوصة.
    HorizontalResolution = 72f,
    VerticalResolution = 72f,

    // يمكننا قياس الصورة باستخدام هذه الخاصية. القيمة الافتراضية هي 1.0 للقياس بنسبة 100٪.
    // يمكننا استخدام هذه الخاصية لإلغاء أي تغييرات في أبعاد الصورة قد يسببها تغيير الدقة.
    Scale = 96f / 72f
};

doc.Save(ArtifactsDir + "ImageSaveOptions.EditImage.png", options);
```

### أنظر أيضا

* class [ImageSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../imagesaveoptions/)
* المجسم [Aspose.Words](../../../)


