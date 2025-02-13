---
title: FieldXE.EntryType
second_title: Aspose.Words for .NET API 参考
description: FieldXE 财产. 获取或设置索引条目类型
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fieldxe/entrytype/
---
## FieldXE.EntryType property

获取或设置索引条目类型。

```csharp
public string EntryType { get; set; }
```

### 例子

演示如何创建 INDEX 字段，然后使用 XE 字段在其中填充条目。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建一个 INDEX 字段，它将为文档中找到的每个 XE 字段显示一个条目。
// 每个条目都会在左侧显示 XE 字段的 Text 属性值
// 以及右侧包含 XE 字段的页面。
// 如果 XE 字段的“Text”属性值相同，
// INDEX 字段会将它们分组到一个条目中。
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// 配置INDEX字段只显示边界内的XE字段
// 一个名为“MainBookmark”的书签，其“EntryType”属性的值为“A”。
// 对于 INDEX 和 XE 字段，“EntryType”属性仅使用其字符串值的第一个字符。
index.BookmarkName = "MainBookmark";
index.EntryType = "A";

Assert.AreEqual(" INDEX  \\b MainBookmark \\f A", index.GetFieldCode());

// 在新页面上，以与值匹配的名称开始书签
// INDEX 字段的“BookmarkName”属性。
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MainBookmark");

// INDEX 字段将选择此条目，因为它在书签内，
// 并且它的条目类型也匹配 INDEX 字段的条目类型。
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 1";
indexEntry.EntryType = "A";

Assert.AreEqual(" XE  \"Index entry 1\" \\f A", indexEntry.GetFieldCode());

// 插入一个不会出现在 INDEX 中的 XE 字段，因为条目类型不匹配。
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 2";
indexEntry.EntryType = "B";

// 结束书签，然后插入一个 XE 字段。
// 与INDEX字段类型相同，但不会出现
// 因为它在书签的边界之外。
builder.EndBookmark("MainBookmark");
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 3";
indexEntry.EntryType = "A";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Filtering.docx");
```

### 也可以看看

* class [FieldXE](../)
* 命名空间 [Aspose.Words.Fields](../../fieldxe/)
* 部件 [Aspose.Words](../../../)


