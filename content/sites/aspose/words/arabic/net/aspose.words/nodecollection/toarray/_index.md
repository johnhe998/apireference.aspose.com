---
title: NodeCollection.ToArray
second_title: Aspose.Words لمراجع .NET API
description: NodeCollection طريقة. ينسخ كل العقد من المجموعة إلى مصفوفة جديدة من العقد.
type: docs
weight: 110
url: /ar/net/aspose.words/nodecollection/toarray/
---
## NodeCollection.ToArray method

ينسخ كل العقد من المجموعة إلى مصفوفة جديدة من العقد.

```csharp
public Node[] ToArray()
```

### قيمة الإرجاع

مجموعة من العقد.

### ملاحظات

يجب ألا تضيف / تزيل العقد أثناء التكرار على مجموعة من العقد لأنها تبطل المكرر وتتطلب تحديثات للمجموعات الحية.

لتتمكن من إضافة / إزالة العقد أثناء التكرار ، استخدم هذه الطريقة لنسخ عقد إلى مصفوفة ذات حجم ثابت ثم تكرارها عبر المصفوفة.

### أمثلة

يوضح كيفية استبدال جميع أشكال مربع النص بأشكال الصور.

```csharp
Document doc = new Document(MyDir + "Textboxes in drawing canvas.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(3, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(1, shapes.Count(s => s.ShapeType == ShapeType.Image));

foreach (Shape shape in shapes)
{
    if (shape.ShapeType == ShapeType.TextBox)
    {
        Shape replacementShape = new Shape(doc, ShapeType.Image);
        replacementShape.ImageData.SetImage(ImageDir + "Logo.jpg");
        replacementShape.Left = shape.Left;
        replacementShape.Top = shape.Top;
        replacementShape.Width = shape.Width;
        replacementShape.Height = shape.Height;
        replacementShape.RelativeHorizontalPosition = shape.RelativeHorizontalPosition;
        replacementShape.RelativeVerticalPosition = shape.RelativeVerticalPosition;
        replacementShape.HorizontalAlignment = shape.HorizontalAlignment;
        replacementShape.VerticalAlignment = shape.VerticalAlignment;
        replacementShape.WrapType = shape.WrapType;
        replacementShape.WrapSide = shape.WrapSide;

        shape.ParentNode.InsertAfter(replacementShape, shape);
        shape.Remove();
    }
}

shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(0, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(4, shapes.Count(s => s.ShapeType == ShapeType.Image));

doc.Save(ArtifactsDir + "Shape.ReplaceTextboxesWithImages.docx");
```

### أنظر أيضا

* class [Node](../../node/)
* class [NodeCollection](../)
* مساحة الاسم [Aspose.Words](../../nodecollection/)
* المجسم [Aspose.Words](../../../)


