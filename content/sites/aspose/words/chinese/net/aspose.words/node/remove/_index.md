---
title: Node.Remove
second_title: Aspose.Words for .NET API 参考
description: Node 方法. 从父级中移除自身
type: docs
weight: 150
url: /zh/net/aspose.words/node/remove/
---
## Node.Remove method

从父级中移除自身。

```csharp
public void Remove()
```

### 例子

演示如何从文档中删除所有带有图像的形状。

```csharp
Document doc = new Document(MyDir + "Images.docx");
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.OfType<Shape>().Count(s => s.HasImage));

foreach (Shape shape in shapes.OfType<Shape>())
    if (shape.HasImage) 
        shape.Remove();

Assert.AreEqual(0, shapes.OfType<Shape>().Count(s => s.HasImage));
```

显示如何从复合节点中删除特定类型的所有子节点。

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Assert.AreEqual(2, doc.GetChildNodes(NodeType.Table, true).Count);

Node curNode = doc.FirstSection.Body.FirstChild;

while (curNode != null)
{
    // 将下一个兄弟节点保存为变量，以防我们在删除该节点后想要移动到它。
    Node nextNode = curNode.NextSibling;

    // 一个section body可以包含Paragraph和Table节点。
    // 如果节点是表，则将其从父节点中移除。
    if (curNode.NodeType == NodeType.Table)
        curNode.Remove();

    curNode = nextNode;
}

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Table, true).Count);
```

### 也可以看看

* class [Node](../)
* 命名空间 [Aspose.Words](../../node/)
* 部件 [Aspose.Words](../../../)


