---
title: FieldListNum.ListLevel
second_title: Aspose.Words for .NET API 参考
description: FieldListNum 财产. 获取或设置列表中的级别覆盖字段的默认行为
type: docs
weight: 30
url: /zh/net/aspose.words.fields/fieldlistnum/listlevel/
---
## FieldListNum.ListLevel property

获取或设置列表中的级别，覆盖字段的默认行为。

```csharp
public string ListLevel { get; set; }
```

### 例子

显示如何使用 LISTNUM 字段对段落进行编号。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// LISTNUM 字段显示一个在每个 LISTNUM 字段处递增的数字。
// 这些字段也有多种选项，允许我们使用它们来模拟编号列表。
FieldListNum field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);

// 列表默认从 1 开始计数，但我们可以将此数字设置为不同的值，例如 0。
// 该字段将显示“0)”。
field.StartingNumber = "0";
builder.Writeln("Paragraph 1");

Assert.AreEqual(" LISTNUM  \\s 0", field.GetFieldCode());

 // LISTNUM 字段为每个列表级别维护单独的计数。
// 在与另一个 LISTNUM 字段相同的段落中插入一个 LISTNUM 字段
// 增加列表级别而不是计数。
// 下一个字段将继续我们在上面开始的计数，并在列表级别 1 显示值“1”。
builder.InsertField(FieldType.FieldListNum, true);

// 此字段将从列表级别 2 开始计数。它将显示值“1”。
builder.InsertField(FieldType.FieldListNum, true);

// 此字段将从列表级别 3 开始计数。它将显示值“1”。
// 不同的列表级别有不同的格式，
// 所以这些字段组合起来会显示一个值“1)a)i)”。
builder.InsertField(FieldType.FieldListNum, true);
builder.Writeln("Paragraph 2");

// 我们插入的下一个 LISTNUM 字段将在列表级别继续计数
// 前一个 LISTNUM 字段已打开。
// 我们可以使用“ListLevel”属性跳转到不同的列表级别。
// 如果这个 LISTNUM 字段停留在列表级别 3，它将显示 "ii)",
// 但是，由于我们已将其移至列表级别 2，它会在该级别继续计数并显示“b)”。
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListLevel = "2";
builder.Writeln("Paragraph 3");

Assert.AreEqual(" LISTNUM  \\l 2", field.GetFieldCode());

// 我们可以设置 ListName 属性来让字段模拟不同的 AUTONUM 字段类型。
// "NumberDefault" 模拟 AUTONUM，"OutlineDefault" 模拟 AUTONUMOUT，
// 并且 "LegalDefault" 模拟 AUTONUMLGL 字段。
// 以 1 为起始编号的“OutlineDefault”列表名称将导致显示“I.”。
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.StartingNumber = "1";
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 4");

Assert.IsTrue(field.HasListName);
Assert.AreEqual(" LISTNUM  OutlineDefault \\s 1", field.GetFieldCode());

// ListName 不会继承前一个字段，因此我们需要为每个新字段设置它。
// 该字段以不同的列表名称继续计数并显示“II.”。
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 5");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.LISTNUM.docx");
```

### 也可以看看

* class [FieldListNum](../)
* 命名空间 [Aspose.Words.Fields](../../fieldlistnum/)
* 部件 [Aspose.Words](../../../)


