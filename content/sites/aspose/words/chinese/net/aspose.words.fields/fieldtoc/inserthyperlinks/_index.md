---
title: FieldToc.InsertHyperlinks
second_title: Aspose.Words for .NET API 参考
description: FieldToc 财产. 获取或设置是否使目录条目超链接
type: docs
weight: 100
url: /zh/net/aspose.words.fields/fieldtoc/inserthyperlinks/
---
## FieldToc.InsertHyperlinks property

获取或设置是否使目录条目超链接。

```csharp
public bool InsertHyperlinks { get; set; }
```

### 例子

显示如何插入目录，并使用基于标题样式的条目填充它。

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");

    // 插入一个 TOC 字段，它将所有标题编译成一个目录。
    // 对于每个标题，此字段将在左侧创建一个带有该标题样式的文本的行，
    // 标题出现在右侧的页面。
    FieldToc field = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

    // 使用 BookmarkName 属性仅列出标题
    // 出现在名称为“MyBookmark”的书签范围内。
    field.BookmarkName = "MyBookmark";

    // 应用了内置标题样式的文本，例如“标题 1”，将被视为标题。
    // 我们可以在此属性中命名要被 TOC 拾取为标题的其他样式及其 TOC 级别。
    field.CustomStyles = "Quote; 6; Intense Quote; 7";

    // 默认情况下，样式/目录级别在 CustomStyles 属性中用逗号分隔，
    // 但我们可以在此属性中设置自定义分隔符。
    doc.FieldOptions.CustomTocStyleSeparator = ";";

    // 配置该字段以排除任何 TOC 级别超出此范围的标题。
    field.HeadingLevelRange = "1-3";

    // TOC 将不显示 TOC 级别在此范围内的标题的页码。
    field.PageNumberOmittingLevelRange = "2-5";

     // 设置一个自定义字符串，将每个标题与其页码分开。
    field.EntrySeparator = "-";
    field.InsertHyperlinks = true;
    field.HideInWebLayout = false;
    field.PreserveLineBreaks = true;
    field.PreserveTabs = true;
    field.UseParagraphOutlineLevel = false;

    InsertNewPageWithHeading(builder, "First entry", "Heading 1");
    builder.Writeln("Paragraph text.");
    InsertNewPageWithHeading(builder, "Second entry", "Heading 1");
    InsertNewPageWithHeading(builder, "Third entry", "Quote");
    InsertNewPageWithHeading(builder, "Fourth entry", "Intense Quote");

    // 这两个标题将省略页码，因为它们在“2-5”范围内。
    InsertNewPageWithHeading(builder, "Fifth entry", "Heading 2");
    InsertNewPageWithHeading(builder, "Sixth entry", "Heading 3");

    // 这个条目没有出现，因为“标题 4”超出了我们之前设置的“1-3”范围。
    InsertNewPageWithHeading(builder, "Seventh entry", "Heading 4");

    builder.EndBookmark("MyBookmark");
    builder.Writeln("Paragraph text.");

    // 此条目不会出现，因为它位于 TOC 指定的书签之外。
    InsertNewPageWithHeading(builder, "Eighth entry", "Heading 1");

    Assert.AreEqual(" TOC  \\b MyBookmark \\t \"Quote; 6; Intense Quote; 7\" \\o 1-3 \\n 2-5 \\p - \\h \\x \\w", field.GetFieldCode());

    field.UpdatePageNumbers();
    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.TOC.docx");

/// <summary>
/// 开始一个新的页面，插入一段指定样式的段落。
/// </summary>
public void InsertNewPageWithHeading(DocumentBuilder builder, string captionText, string styleName)
{
    builder.InsertBreak(BreakType.PageBreak);
    string originalStyle = builder.ParagraphFormat.StyleName;
    builder.ParagraphFormat.Style = builder.Document.Styles[styleName];
    builder.Writeln(captionText);
    builder.ParagraphFormat.Style = builder.Document.Styles[originalStyle];
}
```

### 也可以看看

* class [FieldToc](../)
* 命名空间 [Aspose.Words.Fields](../../fieldtoc/)
* 部件 [Aspose.Words](../../../)


