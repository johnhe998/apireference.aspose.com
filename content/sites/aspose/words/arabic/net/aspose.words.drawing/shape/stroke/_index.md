---
title: Shape.Stroke
second_title: Aspose.Words لمراجع .NET API
description: Shape ملكية. يحدد حد لشكل .
type: docs
weight: 180
url: /ar/net/aspose.words.drawing/shape/stroke/
---
## Shape.Stroke property

يحدد حد لشكل .

```csharp
public Stroke Stroke { get; }
```

### أمثلة

يظهر لإنشاء مجموعة متنوعة من الأشكال.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// فيما يلي أربعة أمثلة للأشكال التي يمكننا إدراجها في مستنداتنا.
// 1 - خط أحمر منقط ، أفقي ، نصف شفاف
// مع سهم على الطرف الأيسر وماسة على الطرف الأيمن:
Shape arrow = new Shape(doc, ShapeType.Line);
arrow.Width = 200;
arrow.Stroke.Color = Color.Red;
arrow.Stroke.StartArrowType = ArrowType.Arrow;
arrow.Stroke.StartArrowLength = ArrowLength.Long;
arrow.Stroke.StartArrowWidth = ArrowWidth.Wide;
arrow.Stroke.EndArrowType = ArrowType.Diamond;
arrow.Stroke.EndArrowLength = ArrowLength.Long;
arrow.Stroke.EndArrowWidth = ArrowWidth.Wide;
arrow.Stroke.DashStyle = DashStyle.Dash;
arrow.Stroke.Opacity = 0.5;

Assert.AreEqual(JoinStyle.Miter, arrow.Stroke.JoinStyle);

builder.InsertNode(arrow);

// 2 - خط قطري أسود سميك بنهايات مستديرة:
Shape line = new Shape(doc, ShapeType.Line);
line.Top = 40;
line.Width = 200;
line.Height = 20;
line.StrokeWeight = 5.0;
line.Stroke.EndCap = EndCap.Round;

builder.InsertNode(line);

// 3 - سهم بتعبئة خضراء:
Shape filledInArrow = new Shape(doc, ShapeType.Arrow);
filledInArrow.Width = 200;
filledInArrow.Height = 40;
filledInArrow.Top = 100;
filledInArrow.Fill.ForeColor = Color.Green;
filledInArrow.Fill.Visible = true;

builder.InsertNode(filledInArrow);

// 4 - سهم ذو اتجاه مقلوب مملوء بشعار Aspose:
Shape filledInArrowImg = new Shape(doc, ShapeType.Arrow);
filledInArrowImg.Width = 200;
filledInArrowImg.Height = 40;
filledInArrowImg.Top = 160;
filledInArrowImg.FlipOrientation = FlipOrientation.Both;

byte[] imageBytes = File.ReadAllBytes(ImageDir + "Logo.jpg");

using (MemoryStream stream = new MemoryStream(imageBytes))
{
    Image image = Image.FromStream(stream);
    // عندما نقلب اتجاه سهمنا ، فإننا نقلب أيضًا الصورة التي يحتوي عليها السهم.
    // اقلب الصورة بالطريقة الأخرى لإلغاء ذلك قبل الحصول على الشكل لعرضه.
    image.RotateFlip(RotateFlipType.RotateNoneFlipXY);

    filledInArrowImg.ImageData.SetImage(image);
    filledInArrowImg.Stroke.JoinStyle = JoinStyle.Round;

    builder.InsertNode(filledInArrowImg);
}

doc.Save(ArtifactsDir + "Drawing.VariousShapes.docx");
```

### أنظر أيضا

* class [Stroke](../../stroke/)
* class [Shape](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shape/)
* المجسم [Aspose.Words](../../../)


