---
title: SvgSaveOptions.ShowPageBorder
second_title: Aspose.Words لمراجع .NET API
description: SvgSaveOptions ملكية. التحكم في إضافة حد إلى مخطط الصفحة. الإعداد الافتراضي هوحقيقي .
type: docs
weight: 80
url: /ar/net/aspose.words.saving/svgsaveoptions/showpageborder/
---
## SvgSaveOptions.ShowPageBorder property

التحكم في إضافة حد إلى مخطط الصفحة. الإعداد الافتراضي هو`حقيقي` .

```csharp
public bool ShowPageBorder { get; set; }
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


