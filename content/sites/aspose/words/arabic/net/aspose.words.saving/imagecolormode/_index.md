---
title: Enum ImageColorMode
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.ImageColorMode تعداد. يحدد وضع الألوان للصور التي تم إنشاؤها لصفحات المستند.
type: docs
weight: 4950
url: /ar/net/aspose.words.saving/imagecolormode/
---
## ImageColorMode enumeration

يحدد وضع الألوان للصور التي تم إنشاؤها لصفحات المستند.

```csharp
public enum ImageColorMode
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | سيتم عرض صفحات المستند كصور ملونة. |
| Grayscale | `1` | سيتم عرض صفحات المستند كصور ذات تدرج رمادي. |
| BlackAndWhite | `2` | سيتم عرض صفحات المستند كصور بالأبيض والأسود. |

### أمثلة

يوضح كيفية تعيين وضع الألوان عند عرض المستندات.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            Assert.That(20000, Is.LessThan(new FileInfo(ImageDir + "Logo.jpg").Length));

            // عندما نحفظ المستند كصورة ، يمكننا تمرير كائن SaveOptions إليه
            // حدد وضع اللون للصورة التي ستنشئها عملية الحفظ.
            // إذا قمنا بتعيين خاصية "ImageColorMode" على "ImageColorMode.BlackAndWhite" ،
            // ستطبق عملية الحفظ تقليل اللون الرمادي أثناء تقديم المستند.
             // إذا قمنا بتعيين خاصية "ImageColorMode" على "ImageColorMode.Grayscale" ،
            // ستؤدي عملية الحفظ إلى تحويل المستند إلى صورة أحادية اللون.
            // إذا قمنا بتعيين خاصية "ImageColorMode" على "بلا" ، فإن عملية الحفظ ستطبق الطريقة الافتراضية
            // والاحتفاظ بجميع ألوان المستند في صورة الإخراج.
            ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png);
            imageSaveOptions.ImageColorMode = imageColorMode;

            doc.Save(ArtifactsDir + "ImageSaveOptions.ColorMode.png", imageSaveOptions);

#if NET48 || JAVA
            switch (imageColorMode)
            {
                case ImageColorMode.None:
                    Assert.That(150000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.Grayscale:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.BlackAndWhite:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
            }
#elif NET5_0_OR_GREATER
            switch (imageColorMode)
            {
                case ImageColorMode.None:
                    Assert.That(120000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.Grayscale:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.BlackAndWhite:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
            }
#endif
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


