---
title: Enum SvgTextOutputMode
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.SvgTextOutputMode تعداد. 
type: docs
weight: 5330
url: /ar/net/aspose.words.saving/svgtextoutputmode/
---
## SvgTextOutputMode enumeration

```csharp
public enum SvgTextOutputMode
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| UseSvgFonts | `0` | يتم استخدام خطوط SVG لتقديم النص. ملاحظة ، ليست كل المتصفحات تدعم خطوط SVG. |
| UseTargetMachineFonts | `1` | يتم استخدام الخطوط المثبتة على الجهاز الهدف لعرض النص. ملاحظة ، إذا كانت بعض الخطوط المستخدمة في المستند غير متوفرة على الجهاز الهدف ، يمكن أن تبدو الوثيقة مختلفة. |
| UsePlacedGlyphs | `2` | يتم تقديم النص باستخدام المنحنيات. ملاحظة ، لن يعمل تحديد النص إذا كنت تستخدم هذا الخيار. |

### أمثلة

يوضح كيفية محاكاة خصائص الصور عند تحويل مستند docx إلى .svg.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// تكوين كائن SvgSaveOptions للحفظ بدون حدود صفحة أو نص قابل للتحديد.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


