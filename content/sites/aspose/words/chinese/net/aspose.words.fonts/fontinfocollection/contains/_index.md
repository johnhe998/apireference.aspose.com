---
title: FontInfoCollection.Contains
second_title: Aspose.Words for .NET API 参考
description: FontInfoCollection 方法. 确定集合是否包含具有给定名称的字体
type: docs
weight: 60
url: /zh/net/aspose.words.fonts/fontinfocollection/contains/
---
## FontInfoCollection.Contains method

确定集合是否包含具有给定名称的字体。

```csharp
public bool Contains(string name)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| name | String | 要查找的字体的不区分大小写的名称。 |

### 返回值

如果在集合中找到该项目，则为真；否则为假。

### 例子

显示有关空白文档中存在的字体的信息。

```csharp
Document doc = new Document();

// 一个空白文档包含 3 种默认字体。文档中的每种字体
// 将有一个对应的 FontInfo 对象，其中包含有关该字体的详细信息。
Assert.AreEqual(3, doc.FontInfos.Count);

Assert.True(doc.FontInfos.Contains("Times New Roman"));
Assert.AreEqual(204, doc.FontInfos["Times New Roman"].Charset);

Assert.True(doc.FontInfos.Contains("Symbol"));
Assert.True(doc.FontInfos.Contains("Arial"));
```

### 也可以看看

* class [FontInfoCollection](../)
* 命名空间 [Aspose.Words.Fonts](../../fontinfocollection/)
* 部件 [Aspose.Words](../../../)


