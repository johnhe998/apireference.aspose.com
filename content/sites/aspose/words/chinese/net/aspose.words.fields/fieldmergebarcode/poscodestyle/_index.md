---
title: FieldMergeBarcode.PosCodeStyle
second_title: Aspose.Words for .NET API 参考
description: FieldMergeBarcode 财产. 获取或设置销售点条形码的样式条形码类型 UPCAUPCEEAN13EAN8有效值不区分大小写为 STDSUP2SUP5CASE.
type: docs
weight: 110
url: /zh/net/aspose.words.fields/fieldmergebarcode/poscodestyle/
---
## FieldMergeBarcode.PosCodeStyle property

获取或设置销售点条形码的样式（条形码类型 UPCA&#x7C;UPCE&#x7C;EAN13&#x7C;EAN8）。有效值（不区分大小写）为 [STD&#x7C;SUP2&#x7C;SUP5&#x7C;CASE].

```csharp
public string PosCodeStyle { get; set; }
```

### 例子

展示如何对 EAN13 条码执行邮件合并。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入一个 MERGEBARCODE 字段，它将在邮件合并期间接受来自数据源的值。
// 此字段会将合并数据源的“MyEAN13Barcode”列中的所有值转换为 EAN13 条形码。
FieldMergeBarcode field = (FieldMergeBarcode)builder.InsertField(FieldType.FieldMergeBarcode, true);
field.BarcodeType = "EAN13";
field.BarcodeValue = "MyEAN13Barcode";

// 在条形下方显示条码的数值。
field.DisplayText = true;
field.PosCodeStyle = "CASE";
field.FixCheckDigit = true;

Assert.AreEqual(FieldType.FieldMergeBarcode, field.Type);
Assert.AreEqual(" MERGEBARCODE  MyEAN13Barcode EAN13 \\t \\p CASE \\x", field.GetFieldCode());
builder.Writeln();

// 创建一个 DataTable，其中有一列与我们的 MERGEBARCODE 字段的 BarcodeValue 同名。
// 邮件合并将为每一行创建一个新页面。每个页面将包含一个 DISPLAYBARCODE 字段，
// 这将显示一个 EAN13 条形码，其中包含来自合并行的值。
DataTable table = new DataTable("Barcodes");
table.Columns.Add("MyEAN13Barcode");
table.Rows.Add(new[] { "501234567890" });
table.Rows.Add(new[] { "123456789012" });

doc.MailMerge.Execute(table);

Assert.AreEqual(FieldType.FieldDisplayBarcode, doc.Range.Fields[0].Type);
Assert.AreEqual("DISPLAYBARCODE \"501234567890\" EAN13 \\t \\p CASE \\x",
    doc.Range.Fields[0].GetFieldCode());
Assert.AreEqual(FieldType.FieldDisplayBarcode, doc.Range.Fields[1].Type);
Assert.AreEqual("DISPLAYBARCODE \"123456789012\" EAN13 \\t \\p CASE \\x",
    doc.Range.Fields[1].GetFieldCode());

doc.Save(ArtifactsDir + "Field.MERGEBARCODE.EAN13.docx");
```

### 也可以看看

* class [FieldMergeBarcode](../)
* 命名空间 [Aspose.Words.Fields](../../fieldmergebarcode/)
* 部件 [Aspose.Words](../../../)


