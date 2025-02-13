---
title: XpsSaveOptions.XpsSaveOptions
second_title: Aspose.Words for .NET API 参考
description: XpsSaveOptions 构造函数. 初始化此类的新实例该实例可用于将文档 保存在Xps格式.
type: docs
weight: 10
url: /zh/net/aspose.words.saving/xpssaveoptions/xpssaveoptions/
---
## XpsSaveOptions() {#constructor}

初始化此类的新实例，该实例可用于将文档 保存在Xps格式.

```csharp
public XpsSaveOptions()
```

### 例子

显示如何限制将出现在已保存 XPS 文档大纲中的标题级别。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入可以用作级别 1、2 和 3 的 TOC 条目的标题。
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

// 创建一个“XpsSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .XPS。
XpsSaveOptions saveOptions = new XpsSaveOptions();

Assert.AreEqual(SaveFormat.Xps, saveOptions.SaveFormat);

// 输出的 XPS 文档将包含一个大纲，一个列出文档正文中标题的目录。
// 单击此大纲中的条目会将我们带到其各自标题的位置。
// 将“HeadingsOutlineLevels”属性设置为“2”，从大纲中排除所有级别高于2的标题。
// 我们在上面插入的最后两个标题不会出现。
saveOptions.OutlineOptions.HeadingsOutlineLevels = 2;

doc.Save(ArtifactsDir + "XpsSaveOptions.OutlineLevels.xps", saveOptions);
```

### 也可以看看

* class [XpsSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../xpssaveoptions/)
* 部件 [Aspose.Words](../../../)

---

## XpsSaveOptions(SaveFormat) {#constructor_1}

初始化此类的新实例，该实例可用于将文档 保存在Xps或者OpenXps格式.

```csharp
public XpsSaveOptions(SaveFormat saveFormat)
```

### 例子

演示如何以折页的形式将文档保存为 XPS 格式。

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// 创建一个“XpsSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .XPS。
XpsSaveOptions xpsOptions = new XpsSaveOptions(SaveFormat.Xps);

// 将“UseBookFoldPrintingSettings”属性设置为“true”以排列内容
// 在输出 XPS 中以帮助我们使用它制作小册子的方式。
// 将“UseBookFoldPrintingSettings”属性设置为“false”以正常渲染 XPS。
xpsOptions.UseBookFoldPrintingSettings = renderTextAsBookFold;

// 如果我们将文档呈现为小册子，我们必须设置“MultiplePages”
// 所有部分的页面设置对象的属性为“MultiplePagesType.BookFoldPrinting”。
if (renderTextAsBookFold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// 一旦我们打印了这个文档，我们可以通过堆叠页面把它变成一个小册子
// 从打印机中出来并向下折叠中间。
doc.Save(ArtifactsDir + "XpsSaveOptions.BookFold.xps", xpsOptions);
```

### 也可以看看

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [XpsSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../xpssaveoptions/)
* 部件 [Aspose.Words](../../../)


