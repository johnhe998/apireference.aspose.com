---
title: HtmlSaveOptions.ExportPageMargins
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定页边距是否导出为 HTMLMHTML 或 EPUB 默认为错误的.
type: docs
weight: 220
url: /zh/net/aspose.words.saving/htmlsaveoptions/exportpagemargins/
---
## HtmlSaveOptions.ExportPageMargins property

指定页边距是否导出为 HTML、MHTML 或 EPUB。 默认为`错误的`.

```csharp
public bool ExportPageMargins { get; set; }
```

### 评论

Aspose.Words 默认不显示页边距区域。 如果任何元素被文档边缘完全或部分剪裁，则显示区域可以使用 这个选项扩展。

### 例子

演示如何在输出 HTML 文档中显示越界对象。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 使用构建器插入不带环绕的形状。
Shape shape = builder.InsertShape(ShapeType.Cube, 200, 200);

shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.WrapType = WrapType.None;

// 负形状位置值可能会将形状置于页面边界之外。
// 如果我们将它导出为 HTML，形状将被截断。
shape.Left = -150;

// 将文档保存为 HTML 时，我们可以传递一个 SaveOptions 对象
// 决定是否调整页面以完全显示越界对象。
// 如果我们将“ExportPageMargins”标志设置为“true”，则该形状将在输出 HTML 中完全可见。
// 如果我们将“ExportPageMargins”标志设置为“false”，
// 我们的文档将显示截断的形状，就像我们在 Microsoft Word 中看到的那样。
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageMargins = exportPageMargins };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html");

if (exportPageMargins)
{
    Assert.True(outDocContents.Contains("<style type=\"text/css\">div.Section1 { margin:70.85pt }</style>"));
    Assert.True(outDocContents.Contains("<div class=\"Section1\"><p style=\"margin-top:0pt; margin-left:151pt; margin-bottom:0pt\">"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));
    Assert.True(outDocContents.Contains("<div><p style=\"margin-top:0pt; margin-left:221.85pt; margin-bottom:0pt\">"));
}
```

### 也可以看看

* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


