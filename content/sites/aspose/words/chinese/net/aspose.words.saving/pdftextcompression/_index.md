---
title: Enum PdfTextCompression
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.PdfTextCompression 枚举. 指定应用于 PDF 文件中除图像之外的所有内容的压缩类型
type: docs
weight: 5250
url: /zh/net/aspose.words.saving/pdftextcompression/
---
## PdfTextCompression enumeration

指定应用于 PDF 文件中除图像之外的所有内容的压缩类型。

```csharp
public enum PdfTextCompression
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| None | `0` | 无压缩。 |
| Flate | `1` | Flate (ZIP) 压缩。 |

### 例子

显示在将文档保存为 PDF 时如何应用文本压缩。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

for (int i = 0; i < 100; i++)
    builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                    "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 将“TextCompression”属性设置为“PdfTextCompression.None”以不应用任何
// 当我们将文档保存为 PDF 时压缩为文本。
// 将“TextCompression”属性设置为“PdfTextCompression.Flate”以应用 ZIP 压缩
// 当我们将文档保存为 PDF 时转换为文本。文件越大，这将产生的影响越大。
options.TextCompression = pdfTextCompression;

doc.Save(ArtifactsDir + "PdfSaveOptions.TextCompression.pdf", options);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


