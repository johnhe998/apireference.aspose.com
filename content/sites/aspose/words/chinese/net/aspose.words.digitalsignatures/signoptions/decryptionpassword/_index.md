---
title: SignOptions.DecryptionPassword
second_title: Aspose.Words for .NET API 参考
description: SignOptions 财产. 解密源文档的密码 默认值为 空字符串Empty .
type: docs
weight: 30
url: /zh/net/aspose.words.digitalsignatures/signoptions/decryptionpassword/
---
## SignOptions.DecryptionPassword property

解密源文档的密码。 默认值为 **空字符串**(Empty ).

```csharp
public string DecryptionPassword { get; set; }
```

### 评论

如果OOXML文档是加密的，你应该提供解密密码 在源文档被签名之前解密。 二进制DOC格式的文档不需要这个。

### 例子

显示如何签署加密的文档文件。

```csharp
// 从 PKCS#12 存储创建 X.509 证书，其中应包含私钥。
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// 创建一个评论、日期和解密密码，这些密码将与我们的新数字签名一起应用。
SignOptions signOptions = new SignOptions
{
    Comments = "Comment",
    SignTime = DateTime.Now,
    DecryptionPassword = "docPassword"
};

// 为未签名的输入文档设置本地系统文件名，为其新的数字签名副本设置输出文件名。
string inputFileName = MyDir + "Encrypted.docx";
string outputFileName = ArtifactsDir + "DigitalSignatureUtil.DecryptionPassword.docx";

DigitalSignatureUtil.Sign(inputFileName, outputFileName, certificateHolder, signOptions);
```

### 也可以看看

* class [SignOptions](../)
* 命名空间 [Aspose.Words.DigitalSignatures](../../signoptions/)
* 部件 [Aspose.Words](../../../)


