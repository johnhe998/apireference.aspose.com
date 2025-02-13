---
title: FieldXE.Text
second_title: Aspose.Words for .NET API 参考
description: FieldXE 财产. 获取或设置条目的文本
type: docs
weight: 70
url: /zh/net/aspose.words.fields/fieldxe/text/
---
## FieldXE.Text property

获取或设置条目的文本。

```csharp
public string Text { get; set; }
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

展示如何使用 XE 字段填充 INDEX 字段的条目，并修改其外观。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建一个 INDEX 字段，它将为文档中找到的每个 XE 字段显示一个条目。
// 每个条目都会在左侧显示 XE 字段的 Text 属性值，
// 以及右侧包含 XE 字段的页码。
// 如果 XE 字段的“Text”属性值相同，
// INDEX 字段会将它们分组到一个条目中。
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.LanguageId = "1033";

// 将此属性的值设置为“A”将按首字母对所有条目进行分组，
// 并将该字母以大写形式放在每个组的上方。
index.Heading = "A";

// 将 INDEX 字段创建的表设置为跨越 2 列。
index.NumberOfColumns = "2";

// 将所有起始字母超出“ac”字符范围的条目设置为被忽略。
index.LetterRange = "a-c";

Assert.AreEqual(" INDEX  \\z 1033 \\h A \\c 2 \\p a-c", index.GetFieldCode());

// 接下来的两个 XE 字段将显示在“A”标题下，
// 它们各自的文本样式也应用于它们的页码。
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apple";
indexEntry.IsItalic = true;

Assert.AreEqual(" XE  Apple \\i", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apricot";
indexEntry.IsBold = true;

Assert.AreEqual(" XE  Apricot \\b", indexEntry.GetFieldCode());

// 接下来的两个 XE 字段都将位于 INDEX 字段目录中的“B”和“C”标题下。
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Banana";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cherry";

// INDEX 字段按字母顺序对所有条目进行排序，因此该条目将与其他两个一起显示在“A”下。
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Avocado";

// 这个条目不会出现，因为它以字母“D”开头，
// 它在 INDEX 字段的 LetterRange 属性定义的“ac”字符范围之外。
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Durian";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Formatting.docx");
```

### 也可以看看

* class [FieldXE](../)
* 命名空间 [Aspose.Words.Fields](../../fieldxe/)
* 部件 [Aspose.Words](../../../)


