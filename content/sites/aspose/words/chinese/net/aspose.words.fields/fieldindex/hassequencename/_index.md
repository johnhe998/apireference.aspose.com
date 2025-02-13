---
title: FieldIndex.HasSequenceName
second_title: Aspose.Words for .NET API 参考
description: FieldIndex 财产. 获取一个值该值指示在构建字段结果时是否应使用序列
type: docs
weight: 60
url: /zh/net/aspose.words.fields/fieldindex/hassequencename/
---
## FieldIndex.HasSequenceName property

获取一个值，该值指示在构建字段结果时是否应使用序列。

```csharp
public bool HasSequenceName { get; }
```

### 例子

展示如何通过组合 INDEX 和 SEQ 字段将文档拆分为多个部分。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建一个 INDEX 字段，它将为文档中找到的每个 XE 字段显示一个条目。
// 每个条目都会在左侧显示 XE 字段的 Text 属性值，
// 以及右侧包含 XE 字段的页码。
// 如果 XE 字段的“Text”属性值相同，
// INDEX 字段会将它们分组到一个条目中。
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// 在 SequenceName 属性中，命名一个 SEQ 字段序列。此 INDEX 字段的每个条目现在也将显示
// 序列计数在创建此条目的 XE 字段位置上的数字。
index.SequenceName = "MySequence";

// 设置将围绕序列和页码的文本，以向用户解释它们的含义。
// 使用此配置创建的条目将在其页码处显示类似“MySequence at 1 on page 1”的内容。
// PageNumberSeparator 和 SequenceSeparator 不能超过 15 个字符。
index.PageNumberSeparator = "\tMySequence at ";
index.SequenceSeparator = " on page ";
Assert.IsTrue(index.HasSequenceName);

Assert.AreEqual(" INDEX  \\s MySequence \\e \"\tMySequence at \" \\d \" on page \"", index.GetFieldCode());

// SEQ 字段显示在每个 SEQ 字段处递增的计数。
// 这些字段还为每个唯一的命名序列维护单独的计数
// 由 SEQ 字段的“SequenceIdentifier”属性标识。
// 插入一个 SEQ 字段，它将“MySequence”序列移动到 1。
// 该字段与普通文档文本没有区别。它不会出现在 INDEX 字段的目录中。
builder.InsertBreak(BreakType.PageBreak);
FieldSeq sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", sequenceField.GetFieldCode());

// 插入一个 XE 字段，它将在 INDEX 字段中创建一个条目。
// 因为“MySequence”在 1 并且这个 XE 字段在第 2 页，以及我们上面定义的自定义分隔符，
// 此字段的 INDEX 条目将在左侧显示“Cat”，在右侧显示“MySequence at 1 on page 2”。
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

Assert.AreEqual(" XE  Cat", indexEntry.GetFieldCode());

// 插入分页符并使用 SEQ 字段将“MySequence”推进到 3。
builder.InsertBreak(BreakType.PageBreak);
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

// 插入一个与上述文本属性相同的 XE 字段。
// INDEX 条目将在“文本”属性中对具有匹配值的 XE 字段进行分组
// 进入一个条目，而不是为每个 XE 字段创建一个条目。
// 因为我们在第 2 页，“MySequence”在 3，所以“, 3 on page 3”将被附加到与上面相同的 INDEX 条目中。
// 该 INDEX 条目的页码部分现在将显示“MySequence at 1 on page 2, 3 on page 3”。
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

// 插入具有新的唯一 Text 属性值的 XE 字段。
// 这将添加一个新条目，MySequence 在第 4 页的 3 处。
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Dog";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Sequence.docx");
```

### 也可以看看

* class [FieldIndex](../)
* 命名空间 [Aspose.Words.Fields](../../fieldindex/)
* 部件 [Aspose.Words](../../../)


