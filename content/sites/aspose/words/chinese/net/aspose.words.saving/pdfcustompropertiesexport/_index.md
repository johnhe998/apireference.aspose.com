---
title: Enum PdfCustomPropertiesExport
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.PdfCustomPropertiesExport 枚举. 指定方式CustomDocumentProperties导出为 PDF 文件
type: docs
weight: 5140
url: /zh/net/aspose.words.saving/pdfcustompropertiesexport/
---
## PdfCustomPropertiesExport enumeration

指定方式[`CustomDocumentProperties`](../../aspose.words/document/customdocumentproperties/)导出为 PDF 文件。

```csharp
public enum PdfCustomPropertiesExport
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| None | `0` | 没有导出自定义属性。 |
| Standard | `1` | 自定义属性导出为 /Info 字典中的条目。 |
| Metadata | `2` | 自定义属性是元数据。 |

### 例子

显示如何在将文档转换为 PDF 时导出自定义属性。

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("Company", "My value");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 将“CustomPropertiesExport”属性设置为“PdfCustomPropertiesExport.None”以丢弃
// 我们将文档保存为 .PDF 时的自定义文档属性。
// 将“CustomPropertiesExport”属性设置为“PdfCustomPropertiesExport.Standard”
// 在输出 PDF 文档中保留自定义属性。
// 将“CustomPropertiesExport”属性设置为“PdfCustomPropertiesExport.Metadata”
// 在 XMP 数据包中保留自定义属性。
options.CustomPropertiesExport = pdfCustomPropertiesExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.CustomPropertiesExport.pdf", options);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


