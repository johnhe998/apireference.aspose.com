---
title: ImageWatermarkOptions.Scale
second_title: Aspose.Words لمراجع .NET API
description: ImageWatermarkOptions ملكية. الحصول على عامل القياس أو تعيينه ككسر من الصورة. القيمة الافتراضية هي 0  auto .
type: docs
weight: 30
url: /ar/net/aspose.words/imagewatermarkoptions/scale/
---
## ImageWatermarkOptions.Scale property

الحصول على عامل القياس أو تعيينه ككسر من الصورة. القيمة الافتراضية هي 0 - auto .

```csharp
public double Scale { get; set; }
```

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentOutOfRangeException | يظهر عندما تكون الوسيطة خارج نطاق القيم الصالحة. |

### ملاحظات

تتراوح القيم الصالحة من 0 إلى 65.5 ضمناً.

يعني المقياس التلقائي أنه سيتم تغيير حجم العلامة المائية إلى أقصى عرض لها وأقصى ارتفاع لها بالنسبة إلى هوامش الصفحة.

### أمثلة

يوضح كيفية إنشاء علامة مائية من صورة في نظام الملفات المحلي.

```csharp
Document doc = new Document();

            // قم بتعديل مظهر العلامة المائية للصورة باستخدام كائن ImageWatermarkOptions ،
            // ثم مررها أثناء إنشاء علامة مائية من ملف صورة.
            ImageWatermarkOptions imageWatermarkOptions = new ImageWatermarkOptions();
            imageWatermarkOptions.Scale = 5;
            imageWatermarkOptions.IsWashout = false;

#if NET48 || JAVA
            doc.Watermark.SetImage(Image.FromFile(ImageDir + "Logo.jpg"), imageWatermarkOptions);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
            {
                doc.Watermark.SetImage(image, imageWatermarkOptions);
            }
#endif

            doc.Save(ArtifactsDir + "Document.ImageWatermark.docx");
```

### أنظر أيضا

* class [ImageWatermarkOptions](../)
* مساحة الاسم [Aspose.Words](../../imagewatermarkoptions/)
* المجسم [Aspose.Words](../../../)


