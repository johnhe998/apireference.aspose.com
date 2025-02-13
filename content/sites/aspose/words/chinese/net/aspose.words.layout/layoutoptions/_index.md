---
title: Class LayoutOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Layout.LayoutOptions 班级. 包含允许控制文档布局过程的选项
type: docs
weight: 3150
url: /zh/net/aspose.words.layout/layoutoptions/
---
## LayoutOptions class

包含允许控制文档布局过程的选项。

```csharp
public class LayoutOptions
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [LayoutOptions](layoutoptions/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Callback](../../aspose.words.layout/layoutoptions/callback/) { get; set; } | 获取或设置[`IPageLayoutCallback`](../ipagelayoutcallback/)页面布局模型使用的实现。 |
| [CommentDisplayMode](../../aspose.words.layout/layoutoptions/commentdisplaymode/) { get; set; } | 获取或设置评论的呈现方式。 默认值为ShowInBalloons. |
| [ContinuousSectionPageNumberingRestart](../../aspose.words.layout/layoutoptions/continuoussectionpagenumberingrestart/) { get; set; } | 获取或设置在连续节 重新开始页码时计算页码的行为模式。 |
| [IgnorePrinterMetrics](../../aspose.words.layout/layoutoptions/ignoreprintermetrics/) { get; set; } | 获取或设置是否忽略“使用打印机度量来布局文档”兼容性选项的指示。 默认为 True。 |
| [RevisionOptions](../../aspose.words.layout/layoutoptions/revisionoptions/) { get; } | 获取修订选项。 |
| [ShowHiddenText](../../aspose.words.layout/layoutoptions/showhiddentext/) { get; set; } | 获取或设置是否呈现文档中的隐藏文本的指示。 默认为 False。 |
| [ShowParagraphMarks](../../aspose.words.layout/layoutoptions/showparagraphmarks/) { get; set; } | 获取或设置是否呈现段落标记的指示。 默认为 False。 |
| [TextShaperFactory](../../aspose.words.layout/layoutoptions/textshaperfactory/) { get; set; } | 获取或设置[`ITextShaperFactory`](../../aspose.words.shaping/itextshaperfactory/)用于高级排版渲染功能的实现。 |

### 评论

您不直接创建此类的实例。使用[`LayoutOptions`](../../aspose.words/document/layoutoptions/)访问此文档的布局选项的属性。

请注意，在更改此类中存在的任何选项后，[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/)应调用 method 以便将更改的选项应用于布局。

### 例子

显示如何在呈现的输出文档中隐藏文本。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// 插入隐藏文本，然后指定我们是否希望从呈现的文档中忽略它。
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

显示如何在呈现的输出文档中显示段落标记。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// 添加一些段落，然后启用段落标记以显示段落的结尾
// 渲染文档时使用 pilcrow (¶) 符号。
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

doc.LayoutOptions.ShowParagraphMarks = showParagraphMarks;

doc.Save(ArtifactsDir + "Document.LayoutOptionsParagraphMarks.pdf");
```

显示如何在呈现的输出文档中更改修订的外观。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入修订，然后将所有修订的颜色更改为绿色。
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// 删除出现在每条修改行左侧的栏。
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### 也可以看看

* 命名空间 [Aspose.Words.Layout](../../aspose.words.layout/)
* 部件 [Aspose.Words](../../)


