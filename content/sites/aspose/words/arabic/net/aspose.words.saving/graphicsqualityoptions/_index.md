---
title: Class GraphicsQualityOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.GraphicsQualityOptions فصل. يسمح بتحديد المزيدGraphics خيارات الجودة.
type: docs
weight: 4780
url: /ar/net/aspose.words.saving/graphicsqualityoptions/
---
## GraphicsQualityOptions class

يسمح بتحديد المزيدGraphics خيارات الجودة.

```csharp
public class GraphicsQualityOptions
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [GraphicsQualityOptions](graphicsqualityoptions/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [CompositingMode](../../aspose.words.saving/graphicsqualityoptions/compositingmode/) { get; set; } | الحصول على أو تعيين قيمة تحدد كيفية رسم الصور المركبة على هذه الرسومات. |
| [CompositingQuality](../../aspose.words.saving/graphicsqualityoptions/compositingquality/) { get; set; } | الحصول على جودة عرض الصور المركبة المرسومة إلى هذه الرسومات أو تعيينها . |
| [InterpolationMode](../../aspose.words.saving/graphicsqualityoptions/interpolationmode/) { get; set; } | الحصول على أو تحديد وضع الاستيفاء المرتبط بهذه الرسومات. |
| [SmoothingMode](../../aspose.words.saving/graphicsqualityoptions/smoothingmode/) { get; set; } | الحصول على جودة العرض لهذه الرسومات أو تعيينها. |
| [StringFormat](../../aspose.words.saving/graphicsqualityoptions/stringformat/) { get; set; } | الحصول على معلومات تخطيط النص أو تعيينها (مثل المحاذاة والاتجاه وعلامات الجدولة) معالجة عرض (مثل إدراج القطع واستبدال الأرقام الوطنية) وميزات OpenType. |
| [TextRenderingHint](../../aspose.words.saving/graphicsqualityoptions/textrenderinghint/) { get; set; } | الحصول على أو تحديد وضع العرض للنص المرتبط بهذه الرسومات . |
| [UseTileFlipMode](../../aspose.words.saving/graphicsqualityoptions/usetileflipmode/) { get; set; } | الحصول على أو تعيين علامة تشير إلى ما إذا كان WrapMode هو TileFlipXY. |

### أمثلة

يوضح كيفية تعيين خيارات جودة العرض أثناء تحويل المستندات إلى تنسيقات صور.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

GraphicsQualityOptions qualityOptions = new GraphicsQualityOptions
{
    SmoothingMode = SmoothingMode.AntiAlias,
    TextRenderingHint = TextRenderingHint.ClearTypeGridFit,
    CompositingMode = CompositingMode.SourceOver,
    CompositingQuality = CompositingQuality.HighQuality,
    InterpolationMode = InterpolationMode.High,
    StringFormat = StringFormat.GenericTypographic
};

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg);
saveOptions.GraphicsQualityOptions = qualityOptions;

doc.Save(ArtifactsDir + "ImageSaveOptions.GraphicsQuality.jpg", saveOptions);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


