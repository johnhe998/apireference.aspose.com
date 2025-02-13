---
title: FieldSeq.BookmarkName
second_title: Aspose.Words for .NET API 参考
description: FieldSeq 财产. 获取或设置一个书签名称该名称引用文档中其他位置而不是当前位置的项目
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fieldseq/bookmarkname/
---
## FieldSeq.BookmarkName property

获取或设置一个书签名称，该名称引用文档中其他位置而不是当前位置的项目。

```csharp
public string BookmarkName { get; set; }
```

### 例子

显示如何组合目录和序列字段。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// TOC 字段可以在其目录中为文档中找到的每个 SEQ 字段创建一个条目。
// 每个条目都包含包含 SEQ 字段的段落，
// 以及该字段出现的页码。
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

// 将此 TOC 字段配置为具有值为“MySequence”的 SequenceIdentifier 属性。
fieldToc.TableOfFiguresLabel = "MySequence";

// 将此 TOC 字段配置为仅选取书签范围内的 SEQ 字段
// 命名为“TOCBookmark”。
fieldToc.BookmarkName = "TOCBookmark";
builder.InsertBreak(BreakType.PageBreak);

Assert.AreEqual(" TOC  \\c MySequence \\b TOCBookmark", fieldToc.GetFieldCode());

// SEQ 字段显示在每个 SEQ 字段处递增的计数。
// 这些字段还为每个唯一的命名序列维护单独的计数
// 由 SEQ 字段的“SequenceIdentifier”属性标识。
// 插入一个序列标识符与 TOC 匹配的 SEQ 字段
// TableOfFiguresLabel 属性。此字段不会在 TOC 中创建条目，因为它在外部
// 书签的边界由“BookmarkName”指定。
builder.Write("MySequence #");
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
builder.Writeln(", will not show up in the TOC because it is outside of the bookmark.");

builder.StartBookmark("TOCBookmark");

// 此 SEQ 字段的序列与 TOC 的“TableOfFiguresLabel”属性匹配，并且在书签的范围内。
// 包含此字段的段落将作为条目显示在目录中。
builder.Write("MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
builder.Writeln(", will show up in the TOC next to the entry for the above caption.");

// 此 SEQ 字段的序列与 TOC 的“TableOfFiguresLabel”属性不匹配，
// 并且在书签的范围内。它的段落不会作为条目出现在目录中。
builder.Write("MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "OtherSequence";
builder.Writeln(", will not show up in the TOC because it's from a different sequence identifier.");

// 此 SEQ 字段的序列与 TOC 的“TableOfFiguresLabel”属性匹配，并且在书签的范围内。
// 该字段还引用了另一个书签。该书签的内容将出现在此 SEQ 字段的 TOC 条目中。
// SEQ 字段本身不会显示该书签的内容。
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.BookmarkName = "SEQBookmark";
Assert.AreEqual(" SEQ  MySequence SEQBookmark", fieldSeq.GetFieldCode());

// 创建一个书签，其内容将显示在 TOC 条目中，因为上面的 SEQ 字段引用它。
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("SEQBookmark");
builder.Write("MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
builder.Writeln(", text from inside SEQBookmark.");
builder.EndBookmark("SEQBookmark");

builder.EndBookmark("TOCBookmark");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SEQ.Bookmark.docx");
```

### 也可以看看

* class [FieldSeq](../)
* 命名空间 [Aspose.Words.Fields](../../fieldseq/)
* 部件 [Aspose.Words](../../../)


