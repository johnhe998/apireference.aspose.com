---
title: Node.IsComposite
second_title: Справочник по API Aspose.Words для .NET
description: Node свойство. Возвращает true если этот узел может содержать другие узлы.
type: docs
weight: 30
url: /ru/net/aspose.words/node/iscomposite/
---
## Node.IsComposite property

Возвращает true, если этот узел может содержать другие узлы.

```csharp
public virtual bool IsComposite { get; }
```

### Стоимость имущества

Этот метод возвращает false, так как Node не может иметь дочерних узлов.

### Примеры

Показывает, как пройти по дереву дочерних узлов составного узла.

```csharp
{
    Document doc = new Document(MyDir + "Paragraphs.docx");

    // Любой узел, который может содержать дочерние узлы, например сам документ, является составным.
    Assert.True(doc.IsComposite);

    // Вызываем рекурсивную функцию, которая будет проходить и печатать все дочерние узлы составного узла.
    TraverseAllNodes(doc, 0);
}

/// <summary>
/// Рекурсивно обходит дерево узлов, печатая тип каждого узла
/// с отступом в зависимости от глубины, а также содержимого всех встроенных узлов.
/// </summary>
public void TraverseAllNodes(CompositeNode parentNode, int depth)
{
    for (Node childNode = parentNode.FirstChild; childNode != null; childNode = childNode.NextSibling)
    {
        Console.Write($"{new string('\t', depth)}{Node.NodeTypeToString(childNode.NodeType)}");

        // Рекурсия к узлу, если это составной узел. В противном случае распечатайте его содержимое, если это встроенный узел.
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

### Смотрите также

* class [Node](../)
* пространство имен [Aspose.Words](../../node/)
* сборка [Aspose.Words](../../../)


