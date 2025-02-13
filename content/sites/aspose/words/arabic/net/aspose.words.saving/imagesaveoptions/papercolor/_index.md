---
title: ImageSaveOptions.PaperColor
second_title: Aspose.Words لمراجع .NET API
description: ImageSaveOptions ملكية. الحصول على أو تعيين لون الخلفية الورق للصور التي تم إنشاؤها.
type: docs
weight: 100
url: /ar/net/aspose.words.saving/imagesaveoptions/papercolor/
---
## ImageSaveOptions.PaperColor property

الحصول على أو تعيين لون الخلفية (الورق) للصور التي تم إنشاؤها.

النظام الأساسيWhite.

```csharp
public Color PaperColor { get; set; }
```

### ملاحظات

عند عرض صفحات المستند التي تحدد لون الخلفية الخاص بها ، فإن لون خلفية المستند سيتجاوز اللون المحدد بواسطة هذه الخاصية.

### أمثلة

يجسد صفحة من مستند Word في صورة ذات خلفية شفافة أو ملونة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Times New Roman";
builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

builder.InsertImage(ImageDir + "Logo.jpg");

// قم بإنشاء كائن "ImageSaveOptions" يمكننا تمريره إلى طريقة "حفظ" المستند
// لتعديل الطريقة التي تعرض بها هذه الطريقة المستند إلى صورة.
ImageSaveOptions imgOptions = new ImageSaveOptions(SaveFormat.Png);

// اضبط خاصية "PaperColor" على لون شفاف لتطبيق شفاف
// خلفية المستند أثناء تحويله إلى صورة.
imgOptions.PaperColor = Color.Transparent;

doc.Save(ArtifactsDir + "ImageSaveOptions.PaperColor.Transparent.png", imgOptions);

// اضبط خاصية "PaperColor" على لون معتم لتطبيق هذا اللون
// كخلفية للوثيقة عندما نعرضها على صورة.
imgOptions.PaperColor = Color.LightCoral;

doc.Save(ArtifactsDir + "ImageSaveOptions.PaperColor.LightCoral.png", imgOptions);
```

### أنظر أيضا

* class [ImageSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../imagesaveoptions/)
* المجسم [Aspose.Words](../../../)


