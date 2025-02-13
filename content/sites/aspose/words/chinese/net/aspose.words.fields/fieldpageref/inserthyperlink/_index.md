---
title: FieldPageRef.InsertHyperlink
second_title: Aspose.Words for .NET API 参考
description: FieldPageRef 财产. 获取或设置是否插入书签段落的超链接
type: docs
weight: 30
url: /zh/net/aspose.words.fields/fieldpageref/inserthyperlink/
---
## FieldPageRef.InsertHyperlink property

获取或设置是否插入书签段落的超链接。

```csharp
public bool InsertHyperlink { get; set; }
```

### 例子

显示插入 PAGEREF 字段以显示书签的相对位置。

```csharp
public void FieldPageRef()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    InsertAndNameBookmark(builder, "MyBookmark1");

    // 插入一个 PAGEREF 字段，显示书签所在的页面。
    // 设置 InsertHyperlink 标志以使该字段也用作书签的可点击链接。
    Assert.AreEqual(" PAGEREF  MyBookmark3 \\h", 
        InsertFieldPageRef(builder, "MyBookmark3", true, false, "Hyperlink to Bookmark3, on page: ").GetFieldCode());

    // 我们可以使用 \p 标志来获取要显示的 PAGEREF 字段
    // 书签相对于字段位置的位置。
    // Bookmark1 是在同一页并且在该字段的上方，所以该字段的显示结果将是“上方”。
    Assert.AreEqual(" PAGEREF  MyBookmark1 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark1", true, true, "Bookmark1 is ").GetFieldCode());

    // Bookmark2 会在同一个页面并且在这个字段的下面，所以这个字段的显示结果会是“下面”。
    Assert.AreEqual(" PAGEREF  MyBookmark2 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark2", true, true, "Bookmark2 is ").GetFieldCode());

    // Bookmark3 将在不同的页面上，因此该字段将显示“在第 2 页上”。
    Assert.AreEqual(" PAGEREF  MyBookmark3 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark3", true, true, "Bookmark3 is ").GetFieldCode());

    InsertAndNameBookmark(builder, "MyBookmark2");
    builder.InsertBreak(BreakType.PageBreak);
    InsertAndNameBookmark(builder, "MyBookmark3");

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.PAGEREF.docx");

/// <summary>
/// 使用文档构建器插入 PAGEREF 字段并设置其属性。
/// </summary>
private static FieldPageRef InsertFieldPageRef(DocumentBuilder builder, string bookmarkName, bool insertHyperlink, bool insertRelativePosition, string textBefore)
{
    builder.Write(textBefore);

    FieldPageRef field = (FieldPageRef)builder.InsertField(FieldType.FieldPageRef, true);
    field.BookmarkName = bookmarkName;
    field.InsertHyperlink = insertHyperlink;
    field.InsertRelativePosition = insertRelativePosition;
    builder.Writeln();

    return field;
}

/// <summary>
/// 使用文档构建器插入命名书签。
/// </summary>
private static void InsertAndNameBookmark(DocumentBuilder builder, string bookmarkName)
{
    builder.StartBookmark(bookmarkName);
    builder.Writeln($"Contents of bookmark \"{bookmarkName}\".");
    builder.EndBookmark(bookmarkName);
}
```

### 也可以看看

* class [FieldPageRef](../)
* 命名空间 [Aspose.Words.Fields](../../fieldpageref/)
* 部件 [Aspose.Words](../../../)


