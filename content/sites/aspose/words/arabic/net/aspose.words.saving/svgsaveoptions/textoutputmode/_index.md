---
title: SvgSaveOptions.TextOutputMode
second_title: Aspose.Words لمراجع .NET API
description: SvgSaveOptions ملكية. الحصول على أو تعيين قيمة تحدد كيفية عرض النص بتنسيق SVG.
type: docs
weight: 90
url: /ar/net/aspose.words.saving/svgsaveoptions/textoutputmode/
---
## SvgSaveOptions.TextOutputMode property

الحصول على أو تعيين قيمة تحدد كيفية عرض النص بتنسيق SVG.

```csharp
public SvgTextOutputMode TextOutputMode { get; set; }
```

### ملاحظات

استخدم هذه الخاصية للحصول على أو ضبط الوضع الخاص بكيفية عرض النص داخل المستند عند الحفظ بتنسيق SVG.

النظام الأساسيUseTargetMachineFonts.

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

* enum [SvgTextOutputMode](../../svgtextoutputmode/)
* class [SvgSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../svgsaveoptions/)
* المجسم [Aspose.Words](../../../)


