---
title: TextWatermarkOptions.Layout
second_title: Aspose.Words for .NET API 参考
description: TextWatermarkOptions 财产. 获取或设置水印的布局默认值为Diagonal.
type: docs
weight: 60
url: /zh/net/aspose.words/textwatermarkoptions/layout/
---
## TextWatermarkOptions.Layout property

获取或设置水印的布局。默认值为Diagonal.

```csharp
public WatermarkLayout Layout { get; set; }
```

### 例子

演示如何创建文本水印。

```csharp
Document doc = new Document();

// 添加纯文本水印。
doc.Watermark.SetText("Aspose Watermark");

// 如果我们希望使用它作为水印来编辑文本格式，
// 我们可以通过在创建水印时传递一个 TextWatermarkOptions 对象来做到这一点。
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// 我们可以像这样从文档中删除水印。
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### 也可以看看

* enum [WatermarkLayout](../../watermarklayout/)
* class [TextWatermarkOptions](../)
* 命名空间 [Aspose.Words](../../textwatermarkoptions/)
* 部件 [Aspose.Words](../../../)


