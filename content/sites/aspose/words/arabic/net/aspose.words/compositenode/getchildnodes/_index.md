---
title: CompositeNode.GetChildNodes
second_title: Aspose.Words لمراجع .NET API
description: CompositeNode طريقة. إرجاع مجموعة مباشرة من العقد الفرعية التي تطابق النوع المحدد.
type: docs
weight: 100
url: /ar/net/aspose.words/compositenode/getchildnodes/
---
## CompositeNode.GetChildNodes method

إرجاع مجموعة مباشرة من العقد الفرعية التي تطابق النوع المحدد.

```csharp
public NodeCollection GetChildNodes(NodeType nodeType, bool isDeep)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| nodeType | NodeType | يحدد نوع العقد المراد تحديدها. |
| isDeep | Boolean | صحيح أن التحديد من جميع العقد الفرعية بشكل متكرر . خطأ للتحديد بين الأطفال المباشرين فقط. |

### قيمة الإرجاع

مجموعة مباشرة من العقد الفرعية من النوع المحدد.

### ملاحظات

دائمًا ما تكون مجموعة العقد التي يتم إرجاعها بهذه الطريقة مباشرة.

دائمًا ما تكون المجموعة الحية متزامنة مع المستند. على سبيل المثال ، إذا قمت بتحديد جميع الأقسام في مستند وقمت بالعدد من خلال collection حذف الأقسام ، فسيتم إزالة القسم من المجموعة على الفور عند إزالته من المستند.

### أمثلة

يوضح كيفية طباعة كافة تعليقات المستند وردودهم.

```csharp
Document doc = new Document(MyDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

// إذا لم يكن للتعليق أصل ، فهو تعليق من "المستوى الأعلى" بدلاً من تعليق من نوع الرد.
// طباعة جميع تعليقات المستوى الأعلى مع أي ردود قد تكون لديهم.
foreach (Comment comment in comments.OfType<Comment>().Where(c => c.Ancestor == null))
{
    Console.WriteLine("Top-level comment:");
    Console.WriteLine($"\t\"{comment.GetText().Trim()}\", by {comment.Author}");
    Console.WriteLine($"Has {comment.Replies.Count} replies");
    foreach (Comment commentReply in comment.Replies)
    {
        Console.WriteLine($"\t\"{commentReply.GetText().Trim()}\", by {commentReply.Author}");
    }
    Console.WriteLine();
}
```

يوضح كيفية استخراج الصور من مستند ، وحفظها في نظام الملفات المحلي كملفات فردية.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// احصل على مجموعة الأشكال من المستند ،
// وحفظ بيانات الصورة لكل شكل مع صورة كملف في نظام الملفات المحلي.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // قد تحتوي بيانات صور الأشكال على صور للعديد من تنسيقات الصور الممكنة. 
        // يمكننا تحديد امتداد ملف لكل صورة تلقائيًا ، بناءً على تنسيقها.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
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

* class [NodeCollection](../../nodecollection/)
* enum [NodeType](../../nodetype/)
* class [CompositeNode](../)
* مساحة الاسم [Aspose.Words](../../compositenode/)
* المجسم [Aspose.Words](../../../)


