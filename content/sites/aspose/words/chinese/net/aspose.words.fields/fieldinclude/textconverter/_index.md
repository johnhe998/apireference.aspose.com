---
title: FieldInclude.TextConverter
second_title: Aspose.Words for .NET API 参考
description: FieldInclude 财产. 获取或设置包含文件格式的文本转换器的名称
type: docs
weight: 50
url: /zh/net/aspose.words.fields/fieldinclude/textconverter/
---
## FieldInclude.TextConverter property

获取或设置包含文件格式的文本转换器的名称。

```csharp
public string TextConverter { get; set; }
```

### 例子

演示如何创建 INCLUDE 字段并设置其属性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 我们可以使用 INCLUDE 字段在本地文件系统中导入另一个文档的一部分。
// 我们使用此字段引用的其他文档的书签包含此导入部分。
FieldInclude field = (FieldInclude)builder.InsertField(FieldType.FieldInclude, true);
field.SourceFullName = MyDir + "Bookmarks.docx";
field.BookmarkName = "MyBookmark1";
field.LockFields = false;
field.TextConverter = "Microsoft Word";

Assert.True(Regex.Match(field.GetFieldCode(), " INCLUDE .* MyBookmark1 \\\\c \"Microsoft Word\"").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INCLUDE.docx");
```

### 也可以看看

* class [FieldInclude](../)
* 命名空间 [Aspose.Words.Fields](../../fieldinclude/)
* 部件 [Aspose.Words](../../../)


