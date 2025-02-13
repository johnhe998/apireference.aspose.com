---
title: PclSaveOptions.SaveFormat
second_title: Aspose.Words for .NET API 参考
description: PclSaveOptions 财产. 指定使用此保存选项对象时文档将保存的格式 只能是Pcl.
type: docs
weight: 40
url: /zh/net/aspose.words.saving/pclsaveoptions/saveformat/
---
## PclSaveOptions.SaveFormat property

指定使用此保存选项对象时文档将保存的格式。 只能是Pcl.

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### 例子

演示如何在将文档保存到 PCL 时栅格化复杂元素。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### 也可以看看

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [PclSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pclsaveoptions/)
* 部件 [Aspose.Words](../../../)


