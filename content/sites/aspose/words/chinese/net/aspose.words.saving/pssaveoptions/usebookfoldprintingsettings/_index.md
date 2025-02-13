---
title: PsSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words for .NET API 参考
description: PsSaveOptions 财产. 获取或设置一个布尔值指示是否应使用小册子打印布局保存文档 如果通过以下方式指定MultiplePages.
type: docs
weight: 30
url: /zh/net/aspose.words.saving/pssaveoptions/usebookfoldprintingsettings/
---
## PsSaveOptions.UseBookFoldPrintingSettings property

获取或设置一个布尔值，指示是否应使用小册子打印布局保存文档， 如果通过以下方式指定[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/).

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### 评论

如果指定了这个选项，[`PageSet`](../../fixedpagesaveoptions/pageset/)保存时被忽略。 此行为与 MS Word 匹配。 如果在页面设置中未指定书本折叠打印设置，此选项将无效。

### 例子

展示如何以折页的形式将文档保存为 Postscript 格式。

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// 创建一个“PsSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 PostScript。
// 将“UseBookFoldPrintingSettings”属性设置为“true”以排列内容
// 在输出 Postscript 文档中，以帮助我们制作小册子的方式。
// 将“UseBookFoldPrintingSettings”属性设置为“false”以正常保存文档。
PsSaveOptions saveOptions = new PsSaveOptions
{
    SaveFormat = SaveFormat.Ps,
    UseBookFoldPrintingSettings = renderTextAsBookFold
};

// 如果我们将文档呈现为小册子，我们必须设置“MultiplePages”
// 所有部分的页面设置对象的属性为“MultiplePagesType.BookFoldPrinting”。
foreach (Section s in doc.Sections)
{
    s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
}

// 一旦我们在页面的两面打印这个文档，我们可以一次将所有页面向下折叠，
// 内容将以创建小册子的方式排列。
doc.Save(ArtifactsDir + "PsSaveOptions.UseBookFoldPrintingSettings.ps", saveOptions);
```

### 也可以看看

* class [PsSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pssaveoptions/)
* 部件 [Aspose.Words](../../../)


