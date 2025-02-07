---
title: ShapeBase.IsDecorative
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. الحصول على أو تعيين العلامة التي تحدد ما إذا كان الشكل مزخرفًا في المستند.
type: docs
weight: 230
url: /ar/net/aspose.words.drawing/shapebase/isdecorative/
---
## ShapeBase.IsDecorative property

الحصول على أو تعيين العلامة التي تحدد ما إذا كان الشكل مزخرفًا في المستند.

```csharp
public bool IsDecorative { get; set; }
```

### ملاحظات

لاحظ أن الشكل ليس فارغًا[`AlternativeText`](../alternativetext/) لا يمكن أن تكون مزخرفة.

### أمثلة

يوضح كيفية ضبط أن الشكل مزخرف.

```csharp
Document doc = new Document(MyDir + "Decorative shapes.docx");

Shape shape = (Shape) doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(shape.IsDecorative);

// إذا لم يكن "AlternativeText" فارغًا ، فلا يمكن أن يكون الشكل مزخرفًا.
// لهذا السبب تغيرت قيمتنا إلى "خطأ".
shape.AlternativeText = "Alternative text.";
Assert.False(shape.IsDecorative);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
// إنشاء شكل جديد كزخرفي.
shape = builder.InsertShape(ShapeType.Rectangle, 100, 100);
shape.IsDecorative = true;

doc.Save(ArtifactsDir + "Shape.IsDecorative.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


