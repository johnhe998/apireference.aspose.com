---
title: BookmarkStart.NodeType
second_title: Aspose.Words لمراجع .NET API
description: BookmarkStart ملكية. عوائدBookmarkStart .
type: docs
weight: 40
url: /ar/net/aspose.words/bookmarkstart/nodetype/
---
## BookmarkStart.NodeType property

عوائدBookmarkStart .

```csharp
public override NodeType NodeType { get; }
```

### أمثلة

يوضح كيفية اجتياز شجرة العقد المركبة الخاصة بالعقد الفرعية.

```csharp
{
    Document doc = new Document(MyDir + "Paragraphs.docx");

    // أي عقدة يمكن أن تحتوي على عقد فرعية ، مثل المستند نفسه ، تكون مركبة.
    Assert.True(doc.IsComposite);

    // استدعاء الدالة العودية التي ستمر خلال وطباعة جميع العقد الفرعية للعقدة المركبة.
    TraverseAllNodes(doc, 0);
}

/// <summary>
/// يجتاز بشكل متكرر شجرة عقدة أثناء طباعة نوع كل عقدة
/// مع مسافة بادئة اعتمادًا على العمق بالإضافة إلى محتويات جميع العقد المضمنة.
/// </summary>
public void TraverseAllNodes(CompositeNode parentNode, int depth)
{
    for (Node childNode = parentNode.FirstChild; childNode != null; childNode = childNode.NextSibling)
    {
        Console.Write($"{new string('\t', depth)}{Node.NodeTypeToString(childNode.NodeType)}");

        // تكرر في العقدة إذا كانت عقدة مركبة. بخلاف ذلك ، اطبع محتوياته إذا كانت عقدة مضمنة.
        if (childNode.IsComposite)
        {
            Console.WriteLine();
            TraverseAllNodes((CompositeNode)childNode, depth + 1);
        }
        else if (childNode is Inline)
        {
            Console.WriteLine($" - \"{childNode.GetText().Trim()}\"");
        }
        else
        {
            Console.WriteLine();
        }
    }
}
```

### أنظر أيضا

* enum [NodeType](../../nodetype/)
* class [BookmarkStart](../)
* مساحة الاسم [Aspose.Words](../../bookmarkstart/)
* المجسم [Aspose.Words](../../../)


