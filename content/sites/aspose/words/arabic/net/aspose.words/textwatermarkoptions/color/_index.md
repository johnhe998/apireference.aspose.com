---
title: TextWatermarkOptions.Color
second_title: Aspose.Words لمراجع .NET API
description: TextWatermarkOptions ملكية. الحصول على لون الخط أو تعيينه. القيمة الافتراضية هي Color.Silver.
type: docs
weight: 20
url: /ar/net/aspose.words/textwatermarkoptions/color/
---
## TextWatermarkOptions.Color property

الحصول على لون الخط أو تعيينه. القيمة الافتراضية هي Color.Silver.

```csharp
public Color Color { get; set; }
```

### أمثلة

يوضح كيفية إنشاء علامة مائية نصية.

```csharp
Document doc = new Document();

// أضف علامة مائية بنص عادي.
doc.Watermark.SetText("Aspose Watermark");

// إذا كنا نرغب في تحرير تنسيق النص باستخدامه كعلامة مائية ،
// يمكننا القيام بذلك عن طريق تمرير كائن TextWatermarkOptions عند إنشاء العلامة المائية.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// يمكننا إزالة علامة مائية من مستند مثل هذا.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### أنظر أيضا

* class [TextWatermarkOptions](../)
* مساحة الاسم [Aspose.Words](../../textwatermarkoptions/)
* المجسم [Aspose.Words](../../../)


