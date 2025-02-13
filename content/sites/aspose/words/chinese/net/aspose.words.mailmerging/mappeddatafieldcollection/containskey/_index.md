---
title: MappedDataFieldCollection.ContainsKey
second_title: Aspose.Words for .NET API 参考
description: MappedDataFieldCollection 方法. 确定集合中是否存在来自文档中指定字段的映射
type: docs
weight: 50
url: /zh/net/aspose.words.mailmerging/mappeddatafieldcollection/containskey/
---
## MappedDataFieldCollection.ContainsKey method

确定集合中是否存在来自文档中指定字段的映射。

```csharp
public bool ContainsKey(string documentFieldName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| documentFieldName | String | 文档中邮件合并字段的区分大小写的名称。 |

### 返回值

如果在集合中找到项目，则为真；否则为假。

### 例子

显示如何映射具有不同名称的数据列和 MERGEFIELD，以便在邮件合并期间在它们之间传输数据。

```csharp
public void MappedDataFieldCollection()
{
    Document doc = CreateSourceDocMappedDataFields();
    DataTable dataTable = CreateSourceTableMappedDataFields();

    // 该表有一个名为“Column2”的列，但没有具有该名称的 MERGEFIELD。
    // 另外，我们有一个名为“Column3”的 MERGEFIELD，但数据源没有具有该名称的列。
    // 如果“Column2”中的数据适合“Column3”MERGEFIELD，
    // 我们可以将该列名映射到“MappedDataFields”键/值对中的 MERGEFIELD。
    MappedDataFieldCollection mappedDataFields = doc.MailMerge.MappedDataFields;

    // 我们可以像这样将数据源列名称链接到 MERGEFIELD 名称。
    mappedDataFields.Add("MergeFieldName", "DataSourceColumnName");

    // 将名为“Column2”的数据源列链接到名为“Column3”的 MERGEFIELD。
    mappedDataFields.Add("Column3", "Column2");

    // MERGEFIELD 名称是相应数据源列名称“值”的“键”。
    Assert.AreEqual("DataSourceColumnName", mappedDataFields["MergeFieldName"]);
    Assert.True(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.True(mappedDataFields.ContainsValue("DataSourceColumnName"));

    // 现在如果我们运行这个邮件合并，“Column3”MERGEFIELDs 将从表的“Column2”获取数据。
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.MappedDataFieldCollection.docx");

    // 我们可以遍历这个集合中的元素。
    Assert.AreEqual(2, mappedDataFields.Count);

    using (IEnumerator<KeyValuePair<string, string>> enumerator = mappedDataFields.GetEnumerator())
        while (enumerator.MoveNext())
            Console.WriteLine(
                $"Column named {enumerator.Current.Value} is mapped to MERGEFIELDs named {enumerator.Current.Key}");

    // 我们也可以从集合中移除元素。
    mappedDataFields.Remove("MergeFieldName");

    Assert.False(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.False(mappedDataFields.ContainsValue("DataSourceColumnName"));

    mappedDataFields.Clear();

    Assert.AreEqual(0, mappedDataFields.Count);
}

/// <summary>
/// 创建一个包含 2 个 MERGEFIELD 的文档，其中一个没有
/// 来自下面方法的数据表中的对应列。
/// </summary>
private static Document CreateSourceDocMappedDataFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column3");

    return doc;
}

/// <summary>
/// 创建一个有2列的数据表，其中一列没有
/// 以上方法对应源文档中的MERGEFIELD。
/// </summary>
private static DataTable CreateSourceTableMappedDataFields()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value1", "Value2" });

    return dataTable;
}
```

### 也可以看看

* class [MappedDataFieldCollection](../)
* 命名空间 [Aspose.Words.MailMerging](../../mappeddatafieldcollection/)
* 部件 [Aspose.Words](../../../)


