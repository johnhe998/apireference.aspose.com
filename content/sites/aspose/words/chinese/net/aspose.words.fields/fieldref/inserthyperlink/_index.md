---
title: FieldRef.InsertHyperlink
second_title: Aspose.Words for .NET API 参考
description: FieldRef 财产. 获取或设置是否创建到书签段落的超链接
type: docs
weight: 40
url: /zh/net/aspose.words.fields/fieldref/inserthyperlink/
---
## FieldRef.InsertHyperlink property

获取或设置是否创建到书签段落的超链接。

```csharp
public bool InsertHyperlink { get; set; }
```

### 例子

显示如何插入 REF 字段以引用书签。

```csharp
public void FieldRef()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");
    builder.InsertFootnote(FootnoteType.Footnote, "MyBookmark footnote #1");
    builder.Write("Text that will appear in REF field");
    builder.InsertFootnote(FootnoteType.Footnote, "MyBookmark footnote #2");
    builder.EndBookmark("MyBookmark");
    builder.MoveToDocumentStart();

    // 我们将应用自定义列表格式，其中尖括号的数量表示我们当前所处的列表级别。
    builder.ListFormat.ApplyNumberDefault();
    builder.ListFormat.ListLevel.NumberFormat = "> \x0000";

    // 插入一个 REF 字段，该字段将包含我们书签中的文本，充当超链接，并复制书签的脚注。
    FieldRef field = InsertFieldRef(builder, "MyBookmark", "", "\n");
    field.IncludeNoteOrComment = true;
    field.InsertHyperlink = true;

    Assert.AreEqual(" REF  MyBookmark \\f \\h", field.GetFieldCode());

    // 插入一个 REF 字段，并显示引用的书签是在它上面还是下面。
    field = InsertFieldRef(builder, "MyBookmark", "The referenced paragraph is ", " this field.\n");
    field.InsertRelativePosition = true;

    Assert.AreEqual(" REF  MyBookmark \\p", field.GetFieldCode());

    // 显示文档中出现的书签的列表编号。
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's paragraph number is ", "\n");
    field.InsertParagraphNumber = true;

    Assert.AreEqual(" REF  MyBookmark \\n", field.GetFieldCode());

    // 显示书签的列表编号，但省略非分隔符，如尖括号。
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's paragraph number, non-delimiters suppressed, is ", "\n");
    field.InsertParagraphNumber = true;
    field.SuppressNonDelimiters = true;

    Assert.AreEqual(" REF  MyBookmark \\n \\t", field.GetFieldCode());

    // 向下移动一级列表。
    builder.ListFormat.ListLevelNumber++;
    builder.ListFormat.ListLevel.NumberFormat = ">> \x0001";

    // 显示书签的列表编号和它上面的所有列表级别的编号。
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's full context paragraph number is ", "\n");
    field.InsertParagraphNumberInFullContext = true;

    Assert.AreEqual(" REF  MyBookmark \\w", field.GetFieldCode());

    builder.InsertBreak(BreakType.PageBreak);

    // 显示此 REF 字段和它所引用的书签之间的列表级别编号。
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's relative paragraph number is ", "\n");
    field.InsertParagraphNumberInRelativeContext = true;

    Assert.AreEqual(" REF  MyBookmark \\r", field.GetFieldCode());

    // 在文档的末尾，书签将在此处显示为列表项。
    builder.Writeln("List level above bookmark");
    builder.ListFormat.ListLevelNumber++;
    builder.ListFormat.ListLevel.NumberFormat = ">>> \x0002";

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.REF.docx");

/// <summary>
/// 让文档生成器插入一个 REF 字段，用它引用一个书签，并在它之前和之后添加文本。
/// </summary>
private static FieldRef InsertFieldRef(DocumentBuilder builder, string bookmarkName, string textBefore, string textAfter)
{
    builder.Write(textBefore);
    FieldRef field = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
    field.BookmarkName = bookmarkName;
    builder.Write(textAfter);
    return field;
}
```

### 也可以看看

* class [FieldRef](../)
* 命名空间 [Aspose.Words.Fields](../../fieldref/)
* 部件 [Aspose.Words](../../../)


