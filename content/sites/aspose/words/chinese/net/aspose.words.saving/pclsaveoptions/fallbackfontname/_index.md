---
title: PclSaveOptions.FallbackFontName
second_title: Aspose.Words for .NET API 参考
description: PclSaveOptions 财产. 将使用的字体名称 如果在打印机和内置字体集合中找不到预期的字体
type: docs
weight: 20
url: /zh/net/aspose.words.saving/pclsaveoptions/fallbackfontname/
---
## PclSaveOptions.FallbackFontName property

将使用的字体名称 如果在打印机和内置字体集合中找不到预期的字体。

```csharp
public string FallbackFontName { get; set; }
```

### 评论

如果未找到回退，则会生成警告并使用“Arial”字体。

### 例子

演示如何声明一种字体，如果原始字体不可用，打印机将应用到打印文本作为替代字体。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.FallbackFontName = "Times New Roman";

// 此文档将指示打印机将“Times New Roman”应用于缺少字体的文本。
// 如果“Times New Roman”也无法使用，打印机将默认使用“Arial”字体。
doc.Save(ArtifactsDir + "PclSaveOptions.SetPrinterFont.pcl", saveOptions);
```

### 也可以看看

* class [PclSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pclsaveoptions/)
* 部件 [Aspose.Words](../../../)


