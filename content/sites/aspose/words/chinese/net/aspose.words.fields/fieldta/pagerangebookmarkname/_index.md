---
title: FieldTA.PageRangeBookmarkName
second_title: Aspose.Words for .NET API 参考
description: FieldTA 财产. 获取或设置书签的名称该书签将插入的页面范围标记为条目的页码
type: docs
weight: 60
url: /zh/net/aspose.words.fields/fieldta/pagerangebookmarkname/
---
## FieldTA.PageRangeBookmarkName property

获取或设置书签的名称，该书签将插入的页面范围标记为条目的页码。

```csharp
public string PageRangeBookmarkName { get; set; }
```

### 例子

展示如何使用 TOA 和 TA 字段构建和自定义权限表。

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // 插入一个 TOA 字段，这将为文档中的每个 TA 字段创建一个条目，
    // 显示每个条目的长引用和页码。
    FieldToa fieldToa = (FieldToa)builder.InsertField(FieldType.FieldTOA, false);

    // 为我们的表设置条目类别。此 TOA 现在将仅包含 TA 字段
    // 在其 EntryCategory 属性中具有匹配值。
    fieldToa.EntryCategory = "1";

    // 此外，索引 1 处的权限表类别是“案例”，
    // 如果我们将此变量设置为 true，它将显示为我们表格的标题。
    fieldToa.UseHeading = true;

    // 我们可以通过命名一个需要在 TOA 范围内的书签来进一步过滤 TA 字段。
    fieldToa.BookmarkName = "MyBookmark";

    // 默认情况下，TA 字段的引用之间会出现一个虚线页面范围的选项卡
    // 及其页码。我们可以用我们放在这个属性上的任何文本来替换它。
    // 插入制表符将保留原始制表符。
    fieldToa.EntrySeparator = " \t p.";

    // 如果我们有多个 TA 条目共享相同的长引用，
    // 它们各自的所有页码都将显示在一行上。
    // 我们可以使用这个属性来指定一个字符串来分隔它们的页码。
    fieldToa.PageNumberListSeparator = " & p. ";

    // 我们可以将其设置为 true 以让我们的表格显示单词“passim”
    // 如果一行中有五个或更多页码。
    fieldToa.UsePassim = true;

    // 一个 TA 字段可以引用一系列页面。
    // 我们可以在这里指定一个字符串出现在此类范围的开始页码和结束页码之间。
    fieldToa.PageRangeSeparator = " to ";

    // TA 字段的格式将延续到我们的表格中。
    // 我们可以通过设置 RemoveEntryFormatting 标志来禁用它。
    fieldToa.RemoveEntryFormatting = true;
    builder.Font.Color = Color.Green;
    builder.Font.Name = "Arial Black";

    Assert.AreEqual(" TOA  \\c 1 \\h \\b MyBookmark \\e \" \t p.\" \\l \" & p. \" \\p \\g \" to \" \\f", fieldToa.GetFieldCode());

    builder.InsertBreak(BreakType.PageBreak);

    // 此 TA 字段不会作为条目出现在 TOA 中，因为它在外部
    // TOA 的 BookmarkName 属性指定的书签边界。
    FieldTA fieldTA = InsertToaEntry(builder, "1", "Source 1");

    Assert.AreEqual(" TA  \\c 1 \\l \"Source 1\"", fieldTA.GetFieldCode());

    // 这个TA字段在书签里面，
    // 但是条目类别与表格的不匹配，所以TA字段不会包含它。
    builder.StartBookmark("MyBookmark");
    fieldTA = InsertToaEntry(builder, "2", "Source 2");

    // 这个条目将出现在表格中。
    fieldTA = InsertToaEntry(builder, "1", "Source 3");

    // TOA 表不显示短引用，
    // 但我们可以将它们用作速记来引用多个 TA 字段引用的庞大源名称。
    fieldTA.ShortCitation = "S.3";

    Assert.AreEqual(" TA  \\c 1 \\l \"Source 3\" \\s S.3", fieldTA.GetFieldCode());

    // 我们可以使用以下属性将页码格式化为粗体/斜体。
    // 如果我们将表格设置为忽略格式，我们仍然会看到这些效果。
    fieldTA = InsertToaEntry(builder, "1", "Source 2");
    fieldTA.IsBold = true;
    fieldTA.IsItalic = true;

    Assert.AreEqual(" TA  \\c 1 \\l \"Source 2\" \\b \\i", fieldTA.GetFieldCode());

    // 我们可以配置 TA 字段以获取其 TOA 条目以引用书签跨越的一系列页面。
    // 请注意，此条目与上面的条目引用相同的源以在我们的表中共享一行。
    // 这一行会有上面条目的页码和这个条目的页码范围，
    // 用表格的页列表和页码范围分隔页码。
    fieldTA = InsertToaEntry(builder, "1", "Source 3");
    fieldTA.PageRangeBookmarkName = "MyMultiPageBookmark";

    builder.StartBookmark("MyMultiPageBookmark");
    builder.InsertBreak(BreakType.PageBreak);
    builder.InsertBreak(BreakType.PageBreak);
    builder.InsertBreak(BreakType.PageBreak);
    builder.EndBookmark("MyMultiPageBookmark");

    Assert.AreEqual(" TA  \\c 1 \\l \"Source 3\" \\r MyMultiPageBookmark", fieldTA.GetFieldCode());

    // 如果我们启用了表的“Passim”功能，则具有 5 个或更多具有相同源的 TA 条目将调用它。
    for (int i = 0; i < 5; i++)
    {
        InsertToaEntry(builder, "1", "Source 4");
    }

    builder.EndBookmark("MyBookmark");

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.TOA.TA.docx");

private static FieldTA InsertToaEntry(DocumentBuilder builder, string entryCategory, string longCitation)
{
    FieldTA field = (FieldTA)builder.InsertField(FieldType.FieldTOAEntry, false);
    field.EntryCategory = entryCategory;
    field.LongCitation = longCitation;

    builder.InsertBreak(BreakType.PageBreak);

    return field;
}
```

### 也可以看看

* class [FieldTA](../)
* 命名空间 [Aspose.Words.Fields](../../fieldta/)
* 部件 [Aspose.Words](../../../)


