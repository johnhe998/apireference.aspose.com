---
title: FieldMergeField.IsMapped
second_title: Aspose.Words for .NET API 参考
description: FieldMergeField 财产. 获取或设置此字段是否为映射字段
type: docs
weight: 30
url: /zh/net/aspose.words.fields/fieldmergefield/ismapped/
---
## FieldMergeField.IsMapped property

获取或设置此字段是否为映射字段。

```csharp
public bool IsMapped { get; set; }
```

### 例子

展示如何使用 MERGEFIELD 字段来执行邮件合并。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建一个数据表，用作邮件合并数据源。
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// 插入一个 MERGEFIELD，其 FieldName 属性设置为数据源中列的名称。
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Courtesy Title";
fieldMergeField.IsMapped = true;
fieldMergeField.IsVerticalFormatting = false;

// 我们可以在合并发生时该字段接受的值之前和之后应用文本。
fieldMergeField.TextBefore = "Dear ";
fieldMergeField.TextAfter = " ";

Assert.AreEqual(" MERGEFIELD  \"Courtesy Title\" \\m \\b \"Dear \" \\f \" \"", fieldMergeField.GetFieldCode());

// 为数据源中的不同列插入另一个 MERGEFIELD。
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Last Name";
fieldMergeField.TextAfter = ":";

doc.UpdateFields();
doc.MailMerge.Execute(table);

Assert.AreEqual("Dear Mr. Doe:\u000cDear Mrs. Cardholder:", doc.GetText().Trim());
```

### 也可以看看

* class [FieldMergeField](../)
* 命名空间 [Aspose.Words.Fields](../../fieldmergefield/)
* 部件 [Aspose.Words](../../../)


