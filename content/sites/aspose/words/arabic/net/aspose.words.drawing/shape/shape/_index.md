---
title: Shape.Shape
second_title: Aspose.Words لمراجع .NET API
description: Shape البناء. إنشاء كائن شكل جديد .
type: docs
weight: 10
url: /ar/net/aspose.words.drawing/shape/shape/
---
## Shape constructor

إنشاء كائن شكل جديد .

```csharp
public Shape(DocumentBase doc, ShapeType shapeType)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| doc | DocumentBase | وثيقة المالك. |
| shapeType | ShapeType | نوع الشكل المراد إنشاؤه. |

### ملاحظات

يجب تحديد خصائص الشكل المطلوبة بعد إنشاء الشكل.

### أمثلة

يوضح كيفية إدراج شكل بصورة من نظام الملفات المحلي في مستند.

```csharp
Document doc = new Document();

// سيقوم المُنشئ العام لفئة "الشكل" بإنشاء شكل بنوع علامة "ShapeMarkupLanguage.Vml".
// إذا كنت بحاجة إلى إنشاء شكل من نوع غير بدائي ، مثل SingleCornerSnipped و TopCornersSnipped و DiagonalCornersSnipped ،
// TopCornersOneRoundedOneSnipped أو SingleCornerRounded أو TopCornersRounded أو DiagonalCornersRounded
// الرجاء استخدام DocumentBuilder.InsertShape.
Shape shape = new Shape(doc, ShapeType.Image);
shape.ImageData.SetImage(ImageDir + "Windows MetaFile.wmf");
shape.Width = 100;
shape.Height = 100;

doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

doc.Save(ArtifactsDir + "Image.FromFile.docx");
```

يوضح كيفية إنشاء مربع نص وتنسيقه.

```csharp
Document doc = new Document();

// إنشاء مربع نص عائم.
Shape textBox = new Shape(doc, ShapeType.TextBox);
textBox.WrapType = WrapType.None;
textBox.Height = 50;
textBox.Width = 200;

// تعيين المحاذاة الأفقية والعمودية للنص داخل الشكل.
textBox.HorizontalAlignment = HorizontalAlignment.Center;
textBox.VerticalAlignment = VerticalAlignment.Top;

// أضف فقرة إلى مربع النص وأضف سلسلة من النص الذي سيعرضه مربع النص.
textBox.AppendChild(new Paragraph(doc));
Paragraph para = textBox.FirstParagraph;
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;
Run run = new Run(doc);
run.Text = "Hello world!";
para.AppendChild(run);

doc.FirstSection.Body.FirstParagraph.AppendChild(textBox);

doc.Save(ArtifactsDir + "Shape.CreateTextBox.docx");
```

### أنظر أيضا

* class [DocumentBase](../../../aspose.words/documentbase/)
* enum [ShapeType](../../shapetype/)
* class [Shape](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shape/)
* المجسم [Aspose.Words](../../../)


