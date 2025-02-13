---
title: FieldAutoNum.SeparatorCharacter
second_title: Aspose.Words for .NET API 参考
description: FieldAutoNum 财产. 获取或设置要使用的分隔符
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fieldautonum/separatorcharacter/
---
## FieldAutoNum.SeparatorCharacter property

获取或设置要使用的分隔符。

```csharp
public string SeparatorCharacter { get; set; }
```

### 例子

显示如何使用自动编号字段对段落进行编号。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 每个 AUTONUM 字段显示 AUTONUM 字段的运行计数的当前值，
// 允许我们像编号列表一样自动对项目进行编号。
// 该字段将显示一个数字“1”。
FieldAutoNum field = (FieldAutoNum)builder.InsertField(FieldType.FieldAutoNum, true);
builder.Writeln("\tParagraph 1.");

Assert.AreEqual(" AUTONUM ", field.GetFieldCode());

field = (FieldAutoNum)builder.InsertField(FieldType.FieldAutoNum, true);
builder.Writeln("\tParagraph 2.");

// 字段结果中紧跟数字后出现的分隔符默认是句号。
// 如果我们将此属性保留为空，我们的第二个 AUTONUM 字段将显示“2”。在文档中。
Assert.IsNull(field.SeparatorCharacter);

// 我们可以设置此属性以应用其字符串的第一个字符作为新的分隔符。
// 在这种情况下，我们的 AUTONUM 字段现在将显示“2:”。
field.SeparatorCharacter = ":";

Assert.AreEqual(" AUTONUM  \\s :", field.GetFieldCode());

doc.Save(ArtifactsDir + "Field.AUTONUM.docx");
```

### 也可以看看

* class [FieldAutoNum](../)
* 命名空间 [Aspose.Words.Fields](../../fieldautonum/)
* 部件 [Aspose.Words](../../../)


