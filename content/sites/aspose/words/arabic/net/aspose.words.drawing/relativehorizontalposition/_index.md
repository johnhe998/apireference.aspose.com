---
title: Enum RelativeHorizontalPosition
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.RelativeHorizontalPosition تعداد. يحدد ما هو الموضع الأفقي لشكل أو إطار نص نسبي.
type: docs
weight: 1060
url: /ar/net/aspose.words.drawing/relativehorizontalposition/
---
## RelativeHorizontalPosition enumeration

يحدد ما هو الموضع الأفقي لشكل أو إطار نص نسبي.

```csharp
public enum RelativeHorizontalPosition
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Margin | `0` | تحديد أن الموضع الأفقي يجب أن يكون متناسبًا مع هوامش الصفحة. |
| Page | `1` | يتم وضع الكائن بالنسبة إلى الحافة اليسرى للصفحة. |
| Column | `2` | يتم وضع الكائن بالنسبة إلى الجانب الأيسر من العمود. |
| Character | `3` | يتم وضع الكائن بالنسبة إلى الجانب الأيسر من الفقرة. |
| LeftMargin | `4` | تحديد أن الموضع الأفقي يجب أن يكون متناسبًا مع الهامش الأيسر للصفحة. |
| RightMargin | `5` | تحديد أن الوضع الأفقي يجب أن يكون متناسبًا مع الهامش الأيمن للصفحة. |
| InsideMargin | `6` | يحدد أن الموضع الأفقي يجب أن يكون نسبيًا للهامش الداخلي للصفحة الحالية (الهامش الأيسر في الصفحات الفردية ، واليمين على الصفحات الزوجية) . |
| OutsideMargin | `7` | يحدد أن الموضع الأفقي يجب أن يكون متعلقًا بالهامش الخارجي للصفحة الحالية (الهامش الأيمن على الصفحات الفردية ، اليسار على الصفحات الزوجية) . |
| Default | `2` | القيمة الافتراضية هيColumn . |

### أمثلة

يوضح كيفية إدراج صورة عائمة في وسط الصفحة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل صورة عائمة ستظهر خلف النص المتداخل وقم بمحاذاة مركز الصفحة.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

يوضح كيفية إدراج صورة واستخدامها كعلامة مائية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل الصورة في الرأس بحيث تكون مرئية في كل صفحة.
Image image = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
Shape shape = builder.InsertImage(image);
shape.WrapType = WrapType.None;
shape.BehindText = true;

// ضع الصورة في منتصف الصفحة.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermark.docx");
```

يوضح كيفية إدراج صورة واستخدامها كعلامة مائية (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل الصورة في الرأس بحيث تكون مرئية في كل صفحة.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

using (SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png"))
{
    builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
    Shape shape = builder.InsertImage(image);
    shape.WrapType = WrapType.None;
    shape.BehindText = true;

    // ضع الصورة في منتصف الصفحة.
    shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
    shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
    shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
    shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;
}

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermarkNetStandard2.docx");
```

### أنظر أيضا

* property [RelativeHorizontalPosition](../shapebase/relativehorizontalposition/)
* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


