---
title: CustomPart.ContentType
second_title: Aspose.Words for .NET API 参考
description: CustomPart 财产. 指定此自定义部件的内容类型
type: docs
weight: 20
url: /zh/net/aspose.words.markup/custompart/contenttype/
---
## CustomPart.ContentType property

指定此自定义部件的内容类型。

```csharp
public string ContentType { get; set; }
```

### 评论

此属性仅适用于[`IsExternal`](../isexternal/)是`错误的`.

默认值为空字符串。有效值必须是非空字符串。

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

* class [CustomPart](../)
* 命名空间 [Aspose.Words.Markup](../../custompart/)
* 部件 [Aspose.Words](../../../)


