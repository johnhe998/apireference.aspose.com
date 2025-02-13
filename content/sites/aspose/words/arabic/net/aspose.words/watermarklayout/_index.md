---
title: Enum WatermarkLayout
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.WatermarkLayout تعداد. يحدد تخطيط العلامة المائية بالنسبة لمركز العلامة المائية.
type: docs
weight: 6370
url: /ar/net/aspose.words/watermarklayout/
---
## WatermarkLayout enumeration

يحدد تخطيط العلامة المائية بالنسبة لمركز العلامة المائية.

```csharp
public enum WatermarkLayout
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Horizontal | `0` | تخطيط أفقي للعلامة المائية. يتوافق مع 0 درجة دوران . |
| Diagonal | `315` | تخطيط قطري للعلامة المائية. يتوافق مع 315 درجة دوران . |

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

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


