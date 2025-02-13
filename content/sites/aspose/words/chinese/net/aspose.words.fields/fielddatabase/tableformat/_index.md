---
title: FieldDatabase.TableFormat
second_title: Aspose.Words for .NET API 参考
description: FieldDatabase 财产. 获取或设置要应用于数据库查询结果的格式
type: docs
weight: 100
url: /zh/net/aspose.words.fields/fielddatabase/tableformat/
---
## FieldDatabase.TableFormat property

获取或设置要应用于数据库查询结果的格式。

```csharp
public string TableFormat { get; set; }
```

### 例子

演示如何从数据库中提取数据并将其作为字段插入到文档中。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 此 DATABASE 字段将对数据库运行查询，并将结果显示在表中。
FieldDatabase field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query = "SELECT * FROM [Products]";

Assert.AreEqual($" DATABASE  \\d \"{DatabaseDir.Replace("\\", "\\\\") + "Northwind.mdb"}\" \\c \"DSN=MS Access Databases\" \\s \"SELECT * FROM [Products]\"", 
    field.GetFieldCode());

// 插入另一个具有更复杂查询的 DATABASE 字段，该查询按总销售额降序排列所有产品。
field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query =
    "SELECT [Products].ProductName, FORMAT(SUM([Order Details].UnitPrice * (1 - [Order Details].Discount) * [Order Details].Quantity), 'Currency') AS GrossSales " +
    "FROM([Products] " +
    "LEFT JOIN[Order Details] ON[Products].[ProductID] = [Order Details].[ProductID]) " +
    "GROUP BY[Products].ProductName " +
    "ORDER BY SUM([Order Details].UnitPrice* (1 - [Order Details].Discount) * [Order Details].Quantity) DESC";

// 这些属性与 LIMIT 和 TOP 子句具有相同的功能。
// 将它们配置为仅显示字段表中查询结果的第 1 到第 10 行。
field.FirstRecord = "1";
field.LastRecord = "10";

// 此属性是我们要用于表格的格式的索引。表格格式列表位于“表格自动套用格式...”菜单中
// 当我们在 Microsoft Word 中创建一个 DATABASE 字段时会显示。索引 #10 对应于“彩色 3”格式。
field.TableFormat = "10";

// FormatAttribute 属性是存储多个标志的整数的字符串表示形式。
// 我们可以通过在该属性中设置不同的标志来应用 TableFormat 属性指向的格式。
// 我们使用的数字是表格样式不同方面对应的值组合的总和。
// 63 代表 1（边框）+ 2（阴影）+ 4（字体）+ 8（颜色）+ 16（自动调整）+ 32（标题行）。
field.FormatAttributes = "63";
field.InsertHeadings = true;
field.InsertOnceOnMailMerge = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATABASE.docx");
```

### 也可以看看

* class [FieldDatabase](../)
* 命名空间 [Aspose.Words.Fields](../../fielddatabase/)
* 部件 [Aspose.Words](../../../)


