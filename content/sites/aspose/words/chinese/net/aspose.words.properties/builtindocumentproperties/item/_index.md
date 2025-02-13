---
title: BuiltInDocumentProperties.Item
second_title: Aspose.Words for .NET API 参考
description: BuiltInDocumentProperties 财产. 返回一个DocumentProperty按属性名称的对象
type: docs
weight: 130
url: /zh/net/aspose.words.properties/builtindocumentproperties/item/
---
## BuiltInDocumentProperties indexer

返回一个[`DocumentProperty`](../../documentproperty/)按属性名称的对象。

```csharp
public override DocumentProperty this[string name] { get; }
```

| 范围 | 描述 |
| --- | --- |
| name | 要检索的属性的不区分大小写的名称。 |

### 评论

属性的字符串名称对应于可用的 typed 属性的名称[`BuiltInDocumentProperties`](../).

如果您请求文档中不存在的属性，但该属性的 name 被识别为有效的内置名称，则新的[`DocumentProperty`](../../documentproperty/) 被创建，添加到集合并返回。新创建的属性被分配 一个默认值（空字符串、零、false 或 DateTime.MinValue，具体取决于内置属性的 type ）。

如果您请求文档中不存在的属性并且 name 未被识别为内置名称，则返回 null。

### 例子

显示如何使用自定义文档属性。

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// 每个文档都包含一个自定义属性的集合，这些属性和内置属性一样，是键值对。
// 文档有一个固定的内置属性列表。用户创建所有自定义属性。 
Assert.AreEqual("Value of custom document property", doc.CustomDocumentProperties["CustomProperty"].ToString());

doc.CustomDocumentProperties.Add("CustomProperty2", "Value of custom document property #2");

Console.WriteLine("Custom Properties:");
foreach (var customDocumentProperty in doc.CustomDocumentProperties)
{
    Console.WriteLine(customDocumentProperty.Name);
    Console.WriteLine($"\tType:\t{customDocumentProperty.Type}");
    Console.WriteLine($"\tValue:\t\"{customDocumentProperty.Value}\"");
}
```

### 也可以看看

* class [DocumentProperty](../../documentproperty/)
* class [BuiltInDocumentProperties](../)
* 命名空间 [Aspose.Words.Properties](../../builtindocumentproperties/)
* 部件 [Aspose.Words](../../../)


