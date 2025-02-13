---
title: Enum PdfPermissions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.PdfPermissions 枚举. 指定允许用户对加密的 PDF 文档进行的操作
type: docs
weight: 5230
url: /zh/net/aspose.words.saving/pdfpermissions/
---
## PdfPermissions enumeration

指定允许用户对加密的 PDF 文档进行的操作。

```csharp
[Flags]
public enum PdfPermissions
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| DisallowAll | `0` | 禁止对 PDF 文档进行所有操作。 这是默认值。 |
| AllowAll | `FFFF` | 允许对 PDF 文档进行所有操作。 |
| ContentCopy | `10` | 通过非受控的操作从文档中复制或提取文本和图形 byContentCopyForAccessibility. |
| ContentCopyForAccessibility | `200` | 提取文本和图形（以支持残障用户的可访问性或用于其他目的）。 |
| ModifyContents | `8` | 通过 控制以外的操作修改文档内容ModifyAnnotations,FillIn， 和DocumentAssembly. |
| ModifyAnnotations | `20` | 添加或修改文本注释，填写交互式表单字段，如果ModifyContentsis 还设置、创建或修改交互式表单字段（包括签名字段）。 |
| FillIn | `100` | 填写现有的交互式表单域（包括签名域），即使ModifyContents 很清楚。 |
| DocumentAssembly | `400` | 组装文档（插入、旋转或删除页面并创建文档大纲项目或缩略图 图像），即使ModifyContents很清楚。 |
| Printing | `4` | 打印文档（可能不是最高质量级别，取决于是否 HighResolutionPrinting也设置）. |
| HighResolutionPrinting | `804` | 将文档打印为一种表示形式，根据实现相关的算法，可以 从中生成 PDF 内容的忠实数字副本。当这个标志被清除时（和 Printing已设置），打印应限于外观的低级表示， 可能质量下降。 |

### 例子

展示如何对已保存的 PDF 文档设置权限。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// 首先禁止所有权限。
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// 扩展权限以允许编辑注释。
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions saveOptions = new PdfSaveOptions();

// 通过“EncryptionDetails”属性启用加密。
saveOptions.EncryptionDetails = encryptionDetails;

// 当我们打开这个文档时，我们需要在访问它的内容之前提供密码。
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


