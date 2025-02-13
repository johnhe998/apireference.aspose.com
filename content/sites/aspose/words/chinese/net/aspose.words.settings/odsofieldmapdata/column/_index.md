---
title: OdsoFieldMapData.Column
second_title: Aspose.Words for .NET API 参考
description: OdsoFieldMapData 财产. 指定外部数据源中列的从零开始的索引该索引应 映射到特定 MERGEFIELD 字段的本地名称 默认值为 0
type: docs
weight: 20
url: /zh/net/aspose.words.settings/odsofieldmapdata/column/
---
## OdsoFieldMapData.Column property

指定外部数据源中列的从零开始的索引，该索引应 映射到特定 MERGEFIELD 字段的本地名称。 默认值为 0。

```csharp
public int Column { get; set; }
```

### 例子

演示如何访问将数据源列映射到合并字段的数据集合。

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// 此集合定义邮件合并如何映射来自数据源的列
// 到预定义的 MERGEFIELD、ADDRESSBLOCK 和 GREETINGLINE 字段。
OdsoFieldMapDataCollection dataCollection = doc.MailMergeSettings.Odso.FieldMapDatas;
Assert.AreEqual(30, dataCollection.Count);

using (IEnumerator<OdsoFieldMapData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Field map data index {index++}, type \"{enumerator.Current.Type}\":");

        Console.WriteLine(
            enumerator.Current.Type != OdsoFieldMappingType.Null
                ? $"\tColumn \"{enumerator.Current.Name}\", number {enumerator.Current.Column} mapped to merge field \"{enumerator.Current.MappedName}\"."
                : "\tNo valid column to field mapping data present.");
    }
}

// 克隆此集合中的元素。
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// 按索引单独使用“RemoveAt”方法元素。
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// 使用“Clear”方法一次清除整个集合。
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### 也可以看看

* class [OdsoFieldMapData](../)
* 命名空间 [Aspose.Words.Settings](../../odsofieldmapdata/)
* 部件 [Aspose.Words](../../../)


