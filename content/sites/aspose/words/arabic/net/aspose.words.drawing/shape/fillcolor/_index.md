---
title: Shape.FillColor
second_title: Aspose.Words لمراجع .NET API
description: Shape ملكية. يحدد لون الفرشاة الذي يملأ المسار المغلق للشكل.
type: docs
weight: 40
url: /ar/net/aspose.words.drawing/shape/fillcolor/
---
## Shape.FillColor property

يحدد لون الفرشاة الذي يملأ المسار المغلق للشكل.

```csharp
public Color FillColor { get; set; }
```

### ملاحظات

هذا هو اختصار لملفColor منشأه.

القيمة الافتراضية هي White.

### أمثلة

يوضح كيفية تعبئة شكل بلون خالص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// اكتب بعض النص ، ثم قم بتغطيته بشكل عائم.
builder.Font.Size = 32;
builder.Writeln("Hello world!");

Shape shape = builder.InsertShape(ShapeType.CloudCallout, RelativeHorizontalPosition.LeftMargin, 25,
    RelativeVerticalPosition.TopMargin, 25, 250, 150, WrapType.None);

// استخدم خاصية "StrokeColor" لتعيين لون المخطط التفصيلي للشكل.
shape.StrokeColor = Color.CadetBlue;

// استخدم خاصية "FillColor" لتعيين لون المنطقة الداخلية للشكل.
shape.FillColor = Color.LightBlue;

// تحدد خاصية "العتامة" مدى شفافية اللون على مقياس من 0-1 ،
// مع كون 1 معتمًا تمامًا ، والصفر غير مرئي.
// يكون ملء الشكل افتراضيًا معتمًا تمامًا ، لذلك لا يمكننا رؤية النص الموجود في أعلى هذا الشكل.
Assert.AreEqual(1.0d, shape.Fill.Opacity);

// اضبط عتامة لون تعبئة الشكل على قيمة أقل حتى نتمكن من رؤية النص تحتها.
shape.Fill.Opacity = 0.3;

doc.Save(ArtifactsDir + "Shape.Fill.docx");
```

### أنظر أيضا

* class [Shape](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shape/)
* المجسم [Aspose.Words](../../../)


