---
title: FieldIndex.Heading
second_title: Aspose.Words for .NET API 参考
description: FieldIndex 财产. 获取或设置出现在任何给定字母的每组条目开头的标题
type: docs
weight: 70
url: /zh/net/aspose.words.fields/fieldindex/heading/
---
## FieldIndex.Heading property

获取或设置出现在任何给定字母的每组条目开头的标题。

```csharp
public string Heading { get; set; }
```

### 例子

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

* class [FieldIndex](../)
* 命名空间 [Aspose.Words.Fields](../../fieldindex/)
* 部件 [Aspose.Words](../../../)


