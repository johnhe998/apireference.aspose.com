---
title: PageSetup.BorderSurroundsFooter
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 指定页面边框是包含还是不包含页脚
type: docs
weight: 60
url: /zh/net/aspose.words/pagesetup/bordersurroundsfooter/
---
## PageSetup.BorderSurroundsFooter property

指定页面边框是包含还是不包含页脚。

```csharp
public bool BorderSurroundsFooter { get; set; }
```

### 评论

注意，更改此属性会影响文档中的所有部分。

### 例子

显示如何将边框应用于页面和页眉/页脚。

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This is the main body text.");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("This is the header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("This is the footer.");
builder.MoveToDocumentEnd();

// 插入蓝色双线边框。
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.Borders.LineStyle = LineStyle.Double;
pageSetup.Borders.Color = Color.Blue;

// 一个部分的 PageSetup 对象有 "BorderSurroundsHeader" 和 "BorderSurroundsFooter" 标志来确定
// 页面边框是否围绕主体文本，还分别包括页眉或页脚。
// 将“BorderSurroundsHeader”标志设置为“true”以用我们的边框包围标题，
// 然后设置“BorderSurroundsFooter”标志以将页脚留在边框之外。
pageSetup.BorderSurroundsHeader = true;
pageSetup.BorderSurroundsFooter = false;

doc.Save(ArtifactsDir + "PageSetup.PageBorder.docx");
```

### 也可以看看

* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


