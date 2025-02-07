---
title: Watermark.SetText
second_title: Aspose.Words لمراجع .NET API
description: Watermark طريقة. يضيف علامة مائية نصية إلى المستند.
type: docs
weight: 40
url: /ar/net/aspose.words/watermark/settext/
---
## SetText(string) {#settext}

يضيف علامة مائية نصية إلى المستند.

```csharp
public void SetText(string text)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| text | String | النص المعروض كعلامة مائية. |

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentOutOfRangeException | يتم رميه عندما يكون طول النص خارج النطاق أو يحتوي النص على مسافات بيضاء فقط. |
| ArgumentNullException | يتم الرمي عندما يكون النص فارغًا . |

### ملاحظات

يجب أن يكون طول النص في النطاق من 1 إلى 200 ضمناً . لا يمكن أن يكون النص فارغًا أو يحتوي على مسافات بيضاء فقط.

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

* class [Watermark](../)
* مساحة الاسم [Aspose.Words](../../watermark/)
* المجسم [Aspose.Words](../../../)

---

## SetText(string, TextWatermarkOptions) {#settext_1}

يضيف علامة مائية نصية إلى المستند.

```csharp
public void SetText(string text, TextWatermarkOptions options)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| text | String | النص المعروض كعلامة مائية. |
| options | TextWatermarkOptions | يحدد خيارات إضافية للعلامة المائية النصية. |

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentOutOfRangeException | يتم رميه عندما يكون طول النص خارج النطاق أو يحتوي النص على مسافات بيضاء فقط. |
| ArgumentNullException | يتم الرمي عندما يكون النص فارغًا . |

### ملاحظات

يجب أن يكون طول النص في النطاق من 1 إلى 200 ضمناً . لا يمكن أن يكون النص فارغًا أو يحتوي على مسافات بيضاء فقط.

إذا[`TextWatermarkOptions`](../../textwatermarkoptions/) فارغة ، سيتم تعيين العلامة المائية مع الخيارات الافتراضية.

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

* class [TextWatermarkOptions](../../textwatermarkoptions/)
* class [Watermark](../)
* مساحة الاسم [Aspose.Words](../../watermark/)
* المجسم [Aspose.Words](../../../)


