---
title: BaseWebExtensionCollection1.Item
second_title: Aspose.Words for .NET API 参考
description: BaseWebExtensionCollection 财产. 获取或设置指定索引处的项目
type: docs
weight: 20
url: /zh/net/aspose.words.webextensions/basewebextensioncollection-1/item/
---
## BaseWebExtensionCollection&lt;T&gt; indexer

获取或设置指定索引处的项目。

```csharp
public T this[int index] { get; set; }
```

| 范围 | 描述 |
| --- | --- |
| index | 项目的从零开始的索引。 |

### 例子

展示如何使用文档的 Web 扩展集合。

```csharp
Document doc = new Document(MyDir + "Web extension.docx");

Assert.AreEqual(1, doc.WebExtensionTaskPanes.Count);

// 打印文档的网络扩展的所有属性。
WebExtensionPropertyCollection webExtensionPropertyCollection = doc.WebExtensionTaskPanes[0].WebExtension.Properties;
using (IEnumerator<WebExtensionProperty> enumerator = webExtensionPropertyCollection.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        WebExtensionProperty webExtensionProperty = enumerator.Current;
        Console.WriteLine($"Binding name: {webExtensionProperty.Name}; Binding value: {webExtensionProperty.Value}");
    }
}

// 删除网络扩展。
doc.WebExtensionTaskPanes.Remove(0);

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### 也可以看看

* class [BaseWebExtensionCollection&lt;T&gt;](../)
* 命名空间 [Aspose.Words.WebExtensions](../../basewebextensioncollection-1/)
* 部件 [Aspose.Words](../../../)


