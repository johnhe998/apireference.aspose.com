---
title: CompositeNode.InsertAfter
second_title: Aspose.Words لمراجع .NET API
description: CompositeNode طريقة. يدخل العقدة المحددة مباشرة بعد العقدة المرجعية المحددة.
type: docs
weight: 140
url: /ar/net/aspose.words/compositenode/insertafter/
---
## CompositeNode.InsertAfter method

يدخل العقدة المحددة مباشرة بعد العقدة المرجعية المحددة.

```csharp
public Node InsertAfter(Node newChild, Node refChild)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| newChild | Node | العقدة المراد إدراجها. |
| refChild | Node | العقدة التي هي العقدة المرجعية. يتم وضع العقدة الجديدة بعد العقدة المرجعية. |

### قيمة الإرجاع

العقدة المدرجة.

### ملاحظات

إذا كانت refChild فارغة ، فسيتم إدراج newChild في بداية قائمة العقد الفرعية.

إذا كان الطفل الجديد موجودًا بالفعل في الشجرة ، فسيتم إزالته أولاً.

إذا تم إنشاء العقدة التي يتم إدراجها من مستند آخر ، فيجب عليك استخدام [`ImportNode`](../../documentbase/importnode/) لاستيراد العقدة إلى المستند الحالي. يمكن بعد ذلك إدراج العقدة المستوردة في المستند الحالي.

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

يوضح كيفية إضافة وتحديث وحذف العقد الفرعية في مجموعة العناصر الفرعية الخاصة بالعقدة المركبة.

```csharp
Document doc = new Document();

// يحتوي المستند الفارغ ، افتراضيًا ، على فقرة واحدة.
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);

// يمكن أن تحتوي العقد المركبة مثل فقرتنا على عقد مركبة ومضمنة أخرى مثل الأطفال.
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Run paragraphText = new Run(doc, "Initial text. ");
paragraph.AppendChild(paragraphText);

// إنشاء ثلاث عقد تشغيل أخرى.
Run run1 = new Run(doc, "Run 1. ");
Run run2 = new Run(doc, "Run 2. ");
Run run3 = new Run(doc, "Run 3. ");

// لن يعرض نص المستند عمليات التشغيل هذه حتى نقوم بإدخالها في عقدة مركبة
// هذا بحد ذاته جزء من شجرة عقدة المستند ، كما فعلنا مع التشغيل الأول.
// يمكننا تحديد مكان محتويات نص العقد التي ندرجها
// في المستند عن طريق تحديد موقع الإدراج المتعلق بعقدة أخرى في الفقرة.
Assert.AreEqual("Initial text.", paragraph.GetText().Trim());

// أدخل المدى الثاني في الفقرة أمام التشغيل الأولي.
paragraph.InsertBefore(run2, paragraphText);

Assert.AreEqual("Run 2. Initial text.", paragraph.GetText().Trim());

// أدخل الجولة الثالثة بعد التشغيل الأولي.
paragraph.InsertAfter(run3, paragraphText);

Assert.AreEqual("Run 2. Initial text. Run 3.", paragraph.GetText().Trim());

// أدخل التشغيل الأول في بداية مجموعة العقد الفرعية للفقرة.
paragraph.PrependChild(run1);

Assert.AreEqual("Run 1. Run 2. Initial text. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(4, paragraph.GetChildNodes(NodeType.Any, true).Count);

// يمكننا تعديل محتويات التشغيل عن طريق تحرير وحذف العقد الفرعية الموجودة.
((Run)paragraph.GetChildNodes(NodeType.Run, true)[1]).Text = "Updated run 2. ";
paragraph.GetChildNodes(NodeType.Run, true).Remove(paragraphText);

Assert.AreEqual("Run 1. Updated run 2. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(3, paragraph.GetChildNodes(NodeType.Any, true).Count);
```

### أنظر أيضا

* class [Node](../../node/)
* class [CompositeNode](../)
* مساحة الاسم [Aspose.Words](../../compositenode/)
* المجسم [Aspose.Words](../../../)


