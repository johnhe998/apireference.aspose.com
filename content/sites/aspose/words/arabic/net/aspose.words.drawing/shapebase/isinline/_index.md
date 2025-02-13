---
title: ShapeBase.IsInline
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. طريقة سريعة لتحديد ما إذا كان الشكل موضوعًا سطريًا مع النص.
type: docs
weight: 280
url: /ar/net/aspose.words.drawing/shapebase/isinline/
---
## ShapeBase.IsInline property

طريقة سريعة لتحديد ما إذا كان الشكل موضوعًا سطريًا مع النص.

```csharp
public bool IsInline { get; }
```

### ملاحظات

له تأثير فقط لأشكال المستوى الأعلى.

### أمثلة

يوضح كيفية تحديد ما إذا كان الشكل سطريًا أم عائمًا.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يوجد أدناه نوعان من أنواع التغليف التي قد تحتوي عليها الأشكال.
// 1 - مضمنة:
builder.Write("Hello world! ");
Shape shape = builder.InsertShape(ShapeType.Rectangle, 100, 100);
shape.FillColor = Color.LightBlue;
builder.Write(" Hello again.");

// يوجد شكل مضمن داخل فقرة بين عناصر فقرة أخرى ، مثل مجموعات النص.
// في Microsoft Word ، يجوز لنا النقر فوق الشكل وسحبه إلى أي فقرة كما لو كانت حرفًا.
// إذا كان الشكل كبيرًا ، فسيؤثر على التباعد الرأسي بين الفقرات.
// لا يمكننا نقل هذا الشكل إلى مكان بدون فقرة.
Assert.AreEqual(WrapType.Inline, shape.WrapType);
Assert.True(shape.IsInline);

// 2 - عائم:
shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin ,200, 
    RelativeVerticalPosition.TopMargin ,200, 100, 100, WrapType.None);
shape.FillColor = Color.Orange;

// ينتمي الشكل العائم إلى الفقرة التي ندرجها فيها ،
// التي يمكننا تحديدها بواسطة رمز المرساة الذي يظهر عند النقر فوق الشكل.
// إذا كان الشكل لا يحتوي على رمز ارتساء مرئي على يساره ،
// سنحتاج إلى تمكين المراسي المرئية عبر "الخيارات" - >; "عرض" - >. "مرساة الكائن".
// في Microsoft Word ، قد نترك هذا الشكل انقر واسحب بحرية إلى أي مكان.
Assert.AreEqual(WrapType.None, shape.WrapType);
Assert.False(shape.IsInline);

doc.Save(ArtifactsDir + "Shape.IsInline.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


