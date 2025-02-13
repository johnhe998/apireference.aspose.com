---
title: PclSaveOptions.AddPrinterFont
second_title: Aspose.Words for .NET API 参考
description: PclSaveOptions 方法. 添加有关由制造商上传到打印机的字体信息
type: docs
weight: 50
url: /zh/net/aspose.words.saving/pclsaveoptions/addprinterfont/
---
## PclSaveOptions.AddPrinterFont method

添加有关由制造商上传到打印机的字体信息。

```csharp
public void AddPrinterFont(string fontFullName, string fontPclName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| fontFullName | String | 字体的全名（例如“Times New Roman Bold Italic”）。 |
| fontPclName | String | Pcl 文档中使用的字体的名称。 |

### 评论

根据 Pcl 规范，任何打印机都需要内置 52 种字体。 但是制造商可以在他们的设备中添加一些其他字体。

### 例子

演示如何让打印机用不同的字体替换特定字体的所有实例。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Courier";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.AddPrinterFont("Courier New", "Courier");

// 打印此文档时，打印机将使用“Courier New”字体
// 访问我们的文档使用“Courier”字体的地方。
doc.Save(ArtifactsDir + "PclSaveOptions.AddPrinterFont.pcl", saveOptions);
```

### 也可以看看

* class [PclSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pclsaveoptions/)
* 部件 [Aspose.Words](../../../)


