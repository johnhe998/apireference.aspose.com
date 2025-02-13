---
title: Story.StoryType
second_title: Aspose.Words لمراجع .NET API
description: Story ملكية. الحصول على نوع هذه القصة .
type: docs
weight: 40
url: /ar/net/aspose.words/story/storytype/
---
## Story.StoryType property

الحصول على نوع هذه القصة .

```csharp
public StoryType StoryType { get; }
```

### أمثلة

يوضح كيفية إزالة كافة الأشكال من العقدة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// استخدم DocumentBuilder لإدراج شكل. هذا شكل مضمّن ،
// التي تحتوي على فقرة أصل ، وهي عقدة فرعية لنص القسم الأول.
builder.InsertShape(ShapeType.Cube, 100.0, 100.0);

Assert.AreEqual(1, doc.GetChildNodes(NodeType.Shape, true).Count);

// يمكننا حذف جميع الأشكال من الفقرات الفرعية لهذا النص.
Assert.AreEqual(StoryType.MainText, doc.FirstSection.Body.StoryType);
doc.FirstSection.Body.DeleteShapes();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Shape, true).Count);
```

### أنظر أيضا

* enum [StoryType](../../storytype/)
* class [Story](../)
* مساحة الاسم [Aspose.Words](../../story/)
* المجسم [Aspose.Words](../../../)


