---
title: PdfEncryptionDetails.OwnerPassword
second_title: Aspose.Words for .NET API 参考
description: PdfEncryptionDetails 财产. 指定加密 PDF 文档的所有者密码
type: docs
weight: 20
url: /zh/net/aspose.words.saving/pdfencryptiondetails/ownerpassword/
---
## PdfEncryptionDetails.OwnerPassword property

指定加密 PDF 文档的所有者密码。

```csharp
public string OwnerPassword { get; set; }
```

### 评论

所有者密码允许用户打开一个加密的 PDF 文档，没有任何访问限制 [`Permissions`](../permissions/).

所有者密码不能与用户密码相同。

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

* class [PdfEncryptionDetails](../)
* 命名空间 [Aspose.Words.Saving](../../pdfencryptiondetails/)
* 部件 [Aspose.Words](../../../)


