---
title: CompositeNode.GetChild
second_title: Aspose.Words لمراجع .NET API
description: CompositeNode طريقة. إرجاع العقدة الفرعية رقم N التي تطابق النوع المحدد.
type: docs
weight: 90
url: /ar/net/aspose.words/compositenode/getchild/
---
## CompositeNode.GetChild method

إرجاع العقدة الفرعية رقم N التي تطابق النوع المحدد.

```csharp
public Node GetChild(NodeType nodeType, int index, bool isDeep)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| nodeType | NodeType | يحدد نوع العقدة الفرعية. |
| index | Int32 | الفهرس الصفري للعقدة الفرعية المراد تحديدها. يُسمح أيضًا بالفهارس السلبية وتشير إلى الوصول من النهاية ، أي -1 يعني العقدة الأخيرة. |
| isDeep | Boolean | صحيح أن التحديد من جميع العقد الفرعية بشكل متكرر . خطأ للتحديد بين الأطفال المباشرين فقط. انظر الملاحظات لمزيد من المعلومات. |

### قيمة الإرجاع

العقدة الفرعية التي تطابق المعايير أو فارغة إذا لم يتم العثور على عقدة مطابقة.

### ملاحظات

إذا كان الفهرس خارج النطاق ، يتم إرجاع قيمة فارغة.

لاحظ أن عُقد الترميز (StructuredDocumentTag وSmartTag) يتم اجتيازها حتى عندما تكون قيمة isDeep = false ويتم استدعاء GetChild لنوع العقدة غير المميزة. على سبيل المثال ، إذا تم التفاف التشغيل الأول في الفقرة في StructuredDocumentTag ، فسيظل يتم إرجاعه بواسطة GetChild (NodeType.Run، 0، false).

### أمثلة

يوضح كيفية تطبيق خصائص نمط الجدول مباشرة على عناصر الجدول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.RowStripe = 3;
tableStyle.CellSpacing = 5;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;

table.Style = tableStyle;

// تتعلق هذه الطريقة بخصائص نمط الجدول مثل تلك التي حددناها أعلاه.
doc.ExpandTableStylesToDirectFormatting();

doc.Save(ArtifactsDir + "Document.TableStyleToDirectFormatting.docx");
```

يوضح كيفية اجتياز مجموعة العقد المركبة الخاصة بالعقد الفرعية.

```csharp
Document doc = new Document();

// أضف شريطين وشكل واحد كعقد فرعية إلى الفقرة الأولى من هذا المستند.
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// لاحظ أن "CustomNodeId" لا يتم حفظه في ملف الإخراج ولا يوجد إلا أثناء عمر العقدة.
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// كرر من خلال مجموعة الفقرة للأطفال المباشرين ،
// وطباعة أي أشكال أو أشكال نجدها بالداخل.
NodeCollection children = paragraph.ChildNodes;

Assert.AreEqual(3, paragraph.ChildNodes.Count);

foreach (Node child in children)
    switch (child.NodeType)
    {
        case NodeType.Run:
            Console.WriteLine("Run contents:");
            Console.WriteLine($"\t\"{child.GetText().Trim()}\"");
            break;
        case NodeType.Shape:
            Shape childShape = (Shape)child;
            Console.WriteLine("Shape:");
            Console.WriteLine($"\t{childShape.ShapeType}, {childShape.Width}x{childShape.Height}");
    }
```

### أنظر أيضا

* class [Node](../../node/)
* enum [NodeType](../../nodetype/)
* class [CompositeNode](../)
* مساحة الاسم [Aspose.Words](../../compositenode/)
* المجسم [Aspose.Words](../../../)


