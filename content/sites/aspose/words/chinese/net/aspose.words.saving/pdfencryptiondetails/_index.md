---
title: Class PdfEncryptionDetails
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.PdfEncryptionDetails 班级. 包含 PDF 文档的加密和访问权限的详细信息
type: docs
weight: 5180
url: /zh/net/aspose.words.saving/pdfencryptiondetails/
---
## PdfEncryptionDetails class

包含 PDF 文档的加密和访问权限的详细信息。

```csharp
public class PdfEncryptionDetails
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [PdfEncryptionDetails](pdfencryptiondetails/)(string, string) | 初始化此类的一个实例。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [OwnerPassword](../../aspose.words.saving/pdfencryptiondetails/ownerpassword/) { get; set; } | 指定加密 PDF 文档的所有者密码。 |
| [Permissions](../../aspose.words.saving/pdfencryptiondetails/permissions/) { get; set; } | 指定允许用户对加密的 PDF 文档进行的操作。 默认值为DisallowAll. |
| [UserPassword](../../aspose.words.saving/pdfencryptiondetails/userpassword/) { get; set; } | 指定打开加密 PDF 文档所需的用户密码。 |

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


