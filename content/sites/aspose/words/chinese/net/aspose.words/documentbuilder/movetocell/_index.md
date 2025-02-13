---
title: DocumentBuilder.MoveToCell
second_title: Aspose.Words for .NET API 参考
description: DocumentBuilder 方法. 将光标移动到当前节中的表格单元格
type: docs
weight: 480
url: /zh/net/aspose.words/documentbuilder/movetocell/
---
## DocumentBuilder.MoveToCell method

将光标移动到当前节中的表格单元格。

```csharp
public void MoveToCell(int tableIndex, int rowIndex, int columnIndex, int characterIndex)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| tableIndex | Int32 | 要移动到的表的索引。 |
| rowIndex | Int32 | 表中行的索引。 |
| columnIndex | Int32 | 表中列的索引。 |
| characterIndex | Int32 | 单元格内字符的索引。 负值允许您指定从单元格末尾开始的位置。使用 -1 移动到 单元格的末尾。 |

### 评论

导航在当前部分的当前故事内执行。

对于索引参数，当index大于等于0时，指定从 开始的索引，0为第一个元素。当 index 小于 0 时，它指定一个 index from 结尾， -1 是最后一个元素。

### 例子

显示如何将文档构建器的光标移动到表格中的单元格。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建一个空的 2x2 表。
builder.StartTable();
builder.InsertCell();
builder.InsertCell();
builder.EndRow();
builder.InsertCell();
builder.InsertCell();
builder.EndTable();

// 因为我们已经用 EndTable 方法结束了表格，
// 文档构建器的光标当前位于表格之外。
// 此光标与 Microsoft Word 的闪烁文本光标具有相同的功能。
// 也可以使用构建器的 MoveTo 方法将其移动到文档中的不同位置。
// 我们可以将光标移回表格内的特定单元格。
builder.MoveToCell(0, 1, 1, 0);
builder.Write("Column 2, cell 2.");

doc.Save(ArtifactsDir + "DocumentBuilder.MoveToCell.docx");
```

### 也可以看看

* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)


