---
title: PdfSaveOptions.EncryptionDetails
second_title: Aspose.Words for .NET API 参考
description: PdfSaveOptions 财产. 获取或设置加密输出 PDF 文档的详细信息
type: docs
weight: 110
url: /zh/net/aspose.words.saving/pdfsaveoptions/encryptiondetails/
---
## PdfSaveOptions.EncryptionDetails property

获取或设置加密输出 PDF 文档的详细信息。

```csharp
public PdfEncryptionDetails EncryptionDetails { get; set; }
```

### 评论

默认值为 null 并且输出文档不会被加密。 当此属性设置为有效时[`PdfEncryptionDetails`](../../pdfencryptiondetails/)object, 则输出的 PDF 文档将被加密。

保存到基于 PDF 1.7 的合规性（包括 PDF/UA-1）时使用 AES-128 加密算法。 保存到基于 PDF 2.0 的合规性时使用 AES-256 加密算法。

PDF/A 合规性禁止加密。保存为 PDF/A 时将忽略此选项。

ContentCopyForAccessibility如果输出文档是加密的，PDF/UA compliance 需要权限。保存到 PDF/UA 时将自动使用此权限。

ContentCopyForAccessibility PDF 2.0 格式不推荐使用权限。 保存到 PDF 2.0 时将忽略此权限。

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

* class [PdfEncryptionDetails](../../pdfencryptiondetails/)
* class [PdfSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pdfsaveoptions/)
* 部件 [Aspose.Words](../../../)


