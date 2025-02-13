---
title: ShapeBase.IsInsertRevision
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. إرجاع صحيح إذا تم إدراج هذا الكائن في Microsoft Word أثناء تمكين تعقب التغييرات.
type: docs
weight: 290
url: /ar/net/aspose.words.drawing/shapebase/isinsertrevision/
---
## ShapeBase.IsInsertRevision property

إرجاع صحيح إذا تم إدراج هذا الكائن في Microsoft Word أثناء تمكين تعقب التغييرات.

```csharp
public bool IsInsertRevision { get; }
```

### أمثلة

يوضح كيفية العمل مع أشكال المراجعة.

```csharp
Document doc = new Document();

Assert.False(doc.TrackRevisions);

// أدخل شكلًا مضمنًا بدون تتبع المراجعات ، مما سيجعل هذا الشكل ليس مراجعة من أي نوع.
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// ابدأ تتبع المراجعات ثم أدخل شكلًا آخر ، والذي سيكون مراجعة.
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

shapes[0].Remove();

// نظرًا لأننا أزلنا هذا الشكل أثناء تتبعنا للتغييرات ،
// يستمر الشكل في المستند ويتم اعتباره مراجعة للحذف.
// سيؤدي قبول هذه المراجعة إلى إزالة الشكل نهائيًا ، وسيؤدي رفضه إلى الاحتفاظ به في المستند.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// وقمنا بإدخال شكل آخر أثناء تتبع التغييرات ، بحيث يتم احتساب هذا الشكل كمراجعة إدراج.
// سيؤدي قبول هذه المراجعة إلى استيعاب هذا الشكل في المستند باعتباره عدم مراجعة ،
// وسيؤدي رفض المراجعة إلى إزالة هذا الشكل نهائيًا.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


