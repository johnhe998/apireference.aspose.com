---
title: Node.Remove
second_title: Aspose.Words لمراجع .NET API
description: Node طريقة. يزيل نفسه من الأصل.
type: docs
weight: 150
url: /ar/net/aspose.words/node/remove/
---
## Node.Remove method

يزيل نفسه من الأصل.

```csharp
public void Remove()
```

### أمثلة

يوضح كيفية حذف كل الأشكال بالصور من مستند.

```csharp
Document doc = new Document(MyDir + "Images.docx");
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.OfType<Shape>().Count(s => s.HasImage));

foreach (Shape shape in shapes.OfType<Shape>())
    if (shape.HasImage) 
        shape.Remove();

Assert.AreEqual(0, shapes.OfType<Shape>().Count(s => s.HasImage));
```

يوضح كيفية إزالة جميع العقد الفرعية من نوع معين من عقدة مركبة.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Assert.AreEqual(2, doc.GetChildNodes(NodeType.Table, true).Count);

Node curNode = doc.FirstSection.Body.FirstChild;

while (curNode != null)
{
    // احفظ العقدة الشقيقة التالية كمتغير في حال أردنا الانتقال إليها بعد حذف هذه العقدة.
    Node nextNode = curNode.NextSibling;

    // يمكن أن يحتوي نص القسم على عقد فقرة وجدول.
    // إذا كانت العقدة عبارة عن جدول ، فقم بإزالتها من الأصل.
    if (curNode.NodeType == NodeType.Table)
        curNode.Remove();

    curNode = nextNode;
}

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Table, true).Count);
```

### أنظر أيضا

* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)


