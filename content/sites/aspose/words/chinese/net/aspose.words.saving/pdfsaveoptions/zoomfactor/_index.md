---
title: PdfSaveOptions.ZoomFactor
second_title: Aspose.Words for .NET API 参考
description: PdfSaveOptions 财产. 获取或设置确定文档缩放系数百分比的值
type: docs
weight: 300
url: /zh/net/aspose.words.saving/pdfsaveoptions/zoomfactor/
---
## PdfSaveOptions.ZoomFactor property

获取或设置确定文档缩放系数（百分比）的值。

```csharp
public int ZoomFactor { get; set; }
```

### 评论

此值仅在以下情况下使用[`ZoomBehavior`](../zoombehavior/)被设定为ZoomFactor.

### 例子

显示如何设置阅读器在打开呈现的 PDF 文档时应用的默认缩放。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
// 将“ZoomBehavior”属性设置为“PdfZoomBehavior.ZoomFactor”以获取 PDF 阅读器
// 当我们打开文档时应用基于百分比的缩放因子。
// 将“ZoomFactor”属性设置为“25”，将缩放因子的值设为 25%。
PdfSaveOptions options = new PdfSaveOptions
{
    ZoomBehavior = PdfZoomBehavior.ZoomFactor,
    ZoomFactor = 25
};

// 当我们使用 Adobe Acrobat 等阅读器打开此文档时，我们将看到文档按实际大小的 1/4 缩放。
doc.Save(ArtifactsDir + "PdfSaveOptions.ZoomBehaviour.pdf", options);
```

### 也可以看看

* class [PdfSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pdfsaveoptions/)
* 部件 [Aspose.Words](../../../)


