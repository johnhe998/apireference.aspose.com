---
title: FindReplaceOptions.SmartParagraphBreakReplacement
second_title: Aspose.Words for .NET API 参考
description: FindReplaceOptions 财产. 获取或设置一个布尔值指示当没有下一个同级段落时是否允许替换段落 break 
type: docs
weight: 140
url: /zh/net/aspose.words.replacing/findreplaceoptions/smartparagraphbreakreplacement/
---
## FindReplaceOptions.SmartParagraphBreakReplacement property

获取或设置一个布尔值，指示当没有下一个同级段落时是否允许替换段落 break 。

默认值为`错误的`.

```csharp
public bool SmartParagraphBreakReplacement { get; set; }
```

### 评论

当没有下一个兄弟段落可以移动所有 child 节点时，此选项允许通过在被替换段落之后查找任何（不一定是兄弟）下一个段落来替换段落分隔符。

### 例子

演示如何从具有嵌套表格的表格单元格中删除段落。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 在第一个单元格中创建带有段落和内表的表格。
builder.StartTable();
builder.InsertCell();
builder.Write("TEXT1");
builder.StartTable();
builder.InsertCell();
builder.EndTable();
builder.EndTable();
builder.Writeln();

FindReplaceOptions options = new FindReplaceOptions();
// 当以下选项设置为 'true' 时，Aspose.Words 将删除段落的文本
// 完全用它的段落标记。否则，Aspose.Words 将模仿 Word 并删除
// 只有段落的文本并保持段落标记完整（当表格跟随文本时）。
options.SmartParagraphBreakReplacement = isSmartParagraphBreakReplacement;
doc.Range.Replace(new Regex(@"TEXT1&p"), "", options);

doc.Save(ArtifactsDir + "Table.RemoveParagraphTextAndMark.docx");
```

### 也可以看看

* class [FindReplaceOptions](../)
* 命名空间 [Aspose.Words.Replacing](../../findreplaceoptions/)
* 部件 [Aspose.Words](../../../)


