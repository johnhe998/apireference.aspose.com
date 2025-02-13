---
title: NodeList.Count
second_title: Aspose.Words for .NET API 参考
description: NodeList 财产. 获取列表中的节点数
type: docs
weight: 10
url: /zh/net/aspose.words/nodelist/count/
---
## NodeList.Count property

获取列表中的节点数。

```csharp
public int Count { get; }
```

### 例子

展示如何使用 XPath 导航 NodeList。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 使用 DocumentBuilder 插入一些节点。
builder.Writeln("Hello world!");

builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();

#if NET48 || JAVA
builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
#elif NET5_0_OR_GREATER || __MOBILE__
using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
    builder.InsertImage(image);
#endif

// 我们的文档包含三个 Run 节点。
NodeList nodeList = doc.SelectNodes("//跑”）;

Assert.AreEqual(3, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Hello world!"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// 使用双斜杠选择所有 Run 节点
// 它们是 Table 节点的间接后代，这将是我们插入的两个单元格内的运行。
nodeList = doc.SelectNodes("//Table//跑”）;

Assert.AreEqual(2, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// 单个正斜杠指定直接后代关系，
// 我们在使用双斜杠时跳过了它。
Assert.AreEqual(doc.SelectNodes(" //表//运行"),
    doc.SelectNodes("//表格/行/单元格/段落/运行"));

// 访问包含我们插入的图像的形状。
nodeList = doc.SelectNodes("//形状”）;

Assert.AreEqual(1, nodeList.Count);

Shape shape = (Shape)nodeList[0];
Assert.True(shape.HasImage);
```

### 也可以看看

* class [NodeList](../)
* 命名空间 [Aspose.Words](../../nodelist/)
* 部件 [Aspose.Words](../../../)


