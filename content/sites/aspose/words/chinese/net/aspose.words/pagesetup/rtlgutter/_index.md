---
title: PageSetup.RtlGutter
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 获取或设置 Microsoft Word 是否根据从右到左的语言或从左到右的语言为部分使用装订线
type: docs
weight: 370
url: /zh/net/aspose.words/pagesetup/rtlgutter/
---
## PageSetup.RtlGutter property

获取或设置 Microsoft Word 是否根据从右到左的语言或从左到右的语言为部分使用装订线。

```csharp
public bool RtlGutter { get; set; }
```

### 例子

显示如何设置装订线边距。

```csharp
Document doc = new Document();

// 插入跨越多页的文本。
DocumentBuilder builder = new DocumentBuilder(doc);
for (int i = 0; i < 6; i++)
{
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                  "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
    builder.InsertBreak(BreakType.PageBreak);
}

// 装订线将空格添加到左侧或右侧页边距，
// 这弥补了书籍中页面的中心折叠侵占页面的布局。
PageSetup pageSetup = doc.Sections[0].PageSetup;

 // 确定我们的页面在页边距内有多少空间用于文本，然后添加一个量来填充页边距。
Assert.AreEqual(470.30d, pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin, 0.01d);

pageSetup.Gutter = 100.0d;

// 将“RtlGutter”属性设置为“true”以将装订线放置在更适合从右到左文本的位置。
pageSetup.RtlGutter = true;

// 将“MultiplePages”属性设置为“MultiplePagesType.MirrorMargins”以交替
// 每页页边距的左/右页边位置。
pageSetup.MultiplePages = MultiplePagesType.MirrorMargins;

doc.Save(ArtifactsDir + "PageSetup.Gutter.docx");
```

### 也可以看看

* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


