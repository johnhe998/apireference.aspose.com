---
title: FieldCitation.SourceTag
second_title: Aspose.Words for .NET API 参考
description: FieldCitation 财产. 获取或设置一个数学值 标签要插入的源元素的值
type: docs
weight: 60
url: /zh/net/aspose.words.fields/fieldcitation/sourcetag/
---
## FieldCitation.SourceTag property

获取或设置一个数学值 **标签**要插入的源元素的值。

```csharp
public string SourceTag { get; set; }
```

### 例子

展示如何使用 CITATION 和 BIBLIOGRAPHY 字段。

```csharp
// 打开一个包含我们可以在其中找到的书目来源的文档
// Microsoft Word via References ->引文与参考书目 ->管理来源。
Document doc = new Document(MyDir + "Bibliography.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Text to be cited with one source.");

// 创建仅包含页码和参考书作者的引文。
FieldCitation fieldCitation = (FieldCitation)builder.InsertField(FieldType.FieldCitation, true);

// 我们使用它们的标签名称来引用源。
fieldCitation.SourceTag = "Book1";
fieldCitation.PageNumber = "85";
fieldCitation.SuppressAuthor = false;
fieldCitation.SuppressTitle = true;
fieldCitation.SuppressYear = true;

Assert.AreEqual(" CITATION  Book1 \\p 85 \\t \\y", fieldCitation.GetFieldCode());

// 创建一个引用两个来源的更详细的引文。
builder.InsertParagraph();
builder.Write("Text to be cited with two sources.");
fieldCitation = (FieldCitation)builder.InsertField(FieldType.FieldCitation, true);
fieldCitation.SourceTag = "Book1";
fieldCitation.AnotherSourceTag = "Book2";
fieldCitation.FormatLanguageId = "en-US";
fieldCitation.PageNumber = "19";
fieldCitation.Prefix = "Prefix ";
fieldCitation.Suffix = " Suffix";
fieldCitation.SuppressAuthor = false;
fieldCitation.SuppressTitle = false;
fieldCitation.SuppressYear = false;
fieldCitation.VolumeNumber = "VII";

Assert.AreEqual(" CITATION  Book1 \\m Book2 \\l en-US \\p 19 \\f \"Prefix \" \\s \" Suffix\" \\v VII", fieldCitation.GetFieldCode());

// 我们可以使用 BIBLIOGRAPHY 字段来显示文档中的所有来源。
builder.InsertBreak(BreakType.PageBreak);
FieldBibliography fieldBibliography = (FieldBibliography)builder.InsertField(FieldType.FieldBibliography, true);
fieldBibliography.FormatLanguageId = "1124";

Assert.AreEqual(" BIBLIOGRAPHY  \\l 1124", fieldBibliography.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.CITATION.docx");
```

### 也可以看看

* class [FieldCitation](../)
* 命名空间 [Aspose.Words.Fields](../../fieldcitation/)
* 部件 [Aspose.Words](../../../)


