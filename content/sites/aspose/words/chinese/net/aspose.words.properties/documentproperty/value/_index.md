---
title: DocumentProperty.Value
second_title: Aspose.Words for .NET API 参考
description: DocumentProperty 财产. 获取或设置属性的值
type: docs
weight: 50
url: /zh/net/aspose.words.properties/documentproperty/value/
---
## DocumentProperty.Value property

获取或设置属性的值。

```csharp
public object Value { get; set; }
```

### 评论

不能为空。

### 例子

显示如何使用内置文档属性。

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// “文档”对象在其成员中包含一些元数据。
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// 文档还在其内置属性中存储元数据。
// 每个内置属性都是文档“BuiltInDocumentProperties”对象的成员。
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // 某些属性可能存储多个值。
    if (docProperty.Value is ICollection<object>)
    {
        foreach (object value in docProperty.Value as ICollection<object>)
            Console.WriteLine($"\tValue:\t\"{value}\"");
    }
    else
    {
        Console.WriteLine($"\tValue:\t\"{docProperty.Value}\"");
    }
}
```

### 也可以看看

* class [DocumentProperty](../)
* 命名空间 [Aspose.Words.Properties](../../documentproperty/)
* 部件 [Aspose.Words](../../../)


