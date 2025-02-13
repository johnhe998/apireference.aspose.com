---
title: FieldToc.TableOfFiguresLabel
second_title: Aspose.Words for .NET API 参考
description: FieldToc 财产. 获取或设置在构建图形表时使用的序列标识符的名称
type: docs
weight: 160
url: /zh/net/aspose.words.fields/fieldtoc/tableoffigureslabel/
---
## FieldToc.TableOfFiguresLabel property

获取或设置在构建图形表时使用的序列标识符的名称。

```csharp
public string TableOfFiguresLabel { get; set; }
```

### 例子

显示如何使用 SEQ 字段填充 TOC 字段的条目。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// TOC 字段可以在其目录中为文档中找到的每个 SEQ 字段创建一个条目。
// 每个条目都包含包含 SEQ 字段的段落和该字段出现的页码。
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

// SEQ 字段显示在每个 SEQ 字段处递增的计数。
// 这些字段还为每个唯一的命名序列维护单独的计数
// 由 SEQ 字段的“SequenceIdentifier”属性标识。
// 使用“TableOfFiguresLabel”属性为 TOC 命名一个主序列。
// 现在，此 TOC 将仅在“SequenceIdentifier”设置为“MySequence”的 SEQ 字段中创建条目。
fieldToc.TableOfFiguresLabel = "MySequence";

// 我们可以在“PrefixedSequenceIdentifier”属性中命名另一个 SEQ 字段序列。
 // 此前缀序列中的 SEQ 字段不会创建 TOC 条目。
// 从主序列 SEQ 字段创建的每个 TOC 条目现在也将显示
// 前缀序列当前在产生条目的主序列 SEQ 字段中打开。
fieldToc.PrefixedSequenceIdentifier = "PrefixSequence";

// 每个 TOC 条目将立即在左侧显示前缀序列计数
// 主序列 SEQ 字段出现的页码。
// 我们可以指定将出现在这两个数字之间的自定义分隔符。
fieldToc.SequenceSeparator = ">";

Assert.AreEqual(" TOC  \\c MySequence \\s PrefixSequence \\d >", fieldToc.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);

// 使用 SEQ 字段填充此 TOC 有两种方法。
// 1 - 插入一个属于 TOC 前缀序列的 SEQ 字段：
// 此字段会将“PrefixSequence”的 SEQ 序列计数加 1。
// 由于该字段不属于识别的主序列
// 通过 TOC 的“TableOfFiguresLabel”属性，它不会作为条目出现。
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();

Assert.AreEqual(" SEQ  PrefixSequence", fieldSeq.GetFieldCode());

// 2 - 插入一个属于 TOC 主序列的 SEQ 字段：
// 此 SEQ 字段将在 TOC 中创建一个条目。
// TOC 条目将包含 SEQ 字段所在的段落以及它出现的页码。
// 此条目还将显示前缀序列当前所处的计数，
// 通过 TOC 的 SeqenceSeparator 属性中的值与页码分隔。
// “PrefixSequence”计数为 1，此主序列 SEQ 字段位于第 2 页，
// 分隔符是“>”，所以条目会显示“1>2”。
builder.Write("First TOC entry, MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", fieldSeq.GetFieldCode());

// 插入一个页面，将前缀序列前移2，插入一个SEQ字段，之后创建一个TOC条目。
// 前缀序列现在在 2，主序列 SEQ 字段在第 3 页，
// 所以 TOC 条目将在其页数处显示“2>3”。
builder.InsertBreak(BreakType.PageBreak);
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
builder.Write("Second TOC entry, MySequence #");
fieldSeq.SequenceIdentifier = "MySequence";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TOC.SEQ.docx");
```

### 也可以看看

* class [FieldToc](../)
* 命名空间 [Aspose.Words.Fields](../../fieldtoc/)
* 部件 [Aspose.Words](../../../)


