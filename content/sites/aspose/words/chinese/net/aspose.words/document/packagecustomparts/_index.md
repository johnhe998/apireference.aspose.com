---
title: Document.PackageCustomParts
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取或设置使用未知关系链接到 OOXML 包的自定义部件任意内容的集合
type: docs
weight: 290
url: /zh/net/aspose.words/document/packagecustomparts/
---
## Document.PackageCustomParts property

获取或设置使用“未知关系”链接到 OOXML 包的自定义部件（任意内容）的集合。

```csharp
public CustomPartCollection PackageCustomParts { get; set; }
```

### 评论

不要将这些自定义部分与自定义 XML 数据混淆。如果您需要访问自定义 XML 部分， 使用[`CustomXmlParts`](../customxmlparts/)财产。

此集合包含 OOXML 部件，其父部件是 OOXML 包，它们的目标是“未知关系”。 有关更多信息，请参阅[`CustomPart`](../../../aspose.words.markup/custompart/).

Aspose.Words 仅将自定义部件加载和保存到 OOXML 文档中。

该属性不能`无效的`.

### 例子

显示如何访问文档的任意自定义部件集合。

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// 克隆第二部分，然后将克隆添加到集合中。
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// 枚举集合并打印每个部分。
using (IEnumerator<CustomPart> enumerator = doc.PackageCustomParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Part index {index}:");
        Console.WriteLine($"\tName:\t\t\t\t{enumerator.Current.Name}");
        Console.WriteLine($"\tContent type:\t\t{enumerator.Current.ContentType}");
        Console.WriteLine($"\tRelationship type:\t{enumerator.Current.RelationshipType}");
        Console.WriteLine(enumerator.Current.IsExternal ?
            "\tSourced from outside the document" :
            $"\tStored within the document, length: {enumerator.Current.Data.Length} bytes");
        index++;
    }
}

// 我们可以从这个集合中单独删除元素，也可以一次全部删除。
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### 也可以看看

* class [CustomPartCollection](../../../aspose.words.markup/custompartcollection/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


