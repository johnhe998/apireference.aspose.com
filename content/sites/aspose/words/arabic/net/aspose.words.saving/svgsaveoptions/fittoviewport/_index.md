---
title: SvgSaveOptions.FitToViewPort
second_title: Aspose.Words لمراجع .NET API
description: SvgSaveOptions ملكية. يحدد ما إذا كان يجب أن يملأ SVG الناتج منطقة منفذ العرض المتاحة نافذة المتصفح أو الحاوية . عند التعيين على العرض الحقيقي وارتفاع الناتج SVG يتم تعيينه على 100.
type: docs
weight: 30
url: /ar/net/aspose.words.saving/svgsaveoptions/fittoviewport/
---
## SvgSaveOptions.FitToViewPort property

يحدد ما إذا كان يجب أن يملأ SVG الناتج منطقة منفذ العرض المتاحة (نافذة المتصفح أو الحاوية) . عند التعيين على العرض الحقيقي وارتفاع الناتج SVG يتم تعيينه على 100٪.

القيمة الافتراضية هي كاذبة.

```csharp
public bool FitToViewPort { get; set; }
```

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

* class [SvgSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../svgsaveoptions/)
* المجسم [Aspose.Words](../../../)


