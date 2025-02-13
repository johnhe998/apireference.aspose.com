---
title: ImageSaveOptions.HorizontalResolution
second_title: Aspose.Words لمراجع .NET API
description: ImageSaveOptions ملكية. الحصول على أو تعيين الدقة الأفقية للصور التي تم إنشاؤها  بالنقاط في البوصة .
type: docs
weight: 30
url: /ar/net/aspose.words.saving/imagesaveoptions/horizontalresolution/
---
## ImageSaveOptions.HorizontalResolution property

الحصول على أو تعيين الدقة الأفقية للصور التي تم إنشاؤها ، بالنقاط في البوصة .

```csharp
public float HorizontalResolution { get; set; }
```

### ملاحظات

هذه الخاصية لها تأثير فقط عند الحفظ بتنسيقات صور نقطية وتؤثر على حجم الإخراج بالبكسل.

القيمة الافتراضية هي 96.

### أمثلة

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


