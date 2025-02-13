---
title: Class DigitalSignatureUtil
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.DigitalSignatures.DigitalSignatureUtil 班级. 提供签署文件的方法
type: docs
weight: 400
url: /zh/net/aspose.words.digitalsignatures/digitalsignatureutil/
---
## DigitalSignatureUtil class

提供签署文件的方法。

```csharp
public static class DigitalSignatureUtil
```

## 方法

| 姓名 | 描述 |
| --- | --- |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures)(Stream) | 使用流从文档中加载数字签名。 |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures_1)(string) | 从文档加载数字签名。 |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures)(Stream, Stream) | 从源流中的文档中删除所有数字签名，并将未签名的文档写入目标流。 |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures_1)(string, string) | 从源文件中删除所有数字签名并将未签名的文件写入目标文件。 |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign)(Stream, Stream, CertificateHolder) | 使用给定的符号源文档[`CertificateHolder`](../certificateholder/)使用数字签名 并将签名文档写入目标流。 |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_2)(string, string, CertificateHolder) | 使用给定的符号源文档[`CertificateHolder`](../certificateholder/)使用数字签名 并将签名文档写入目标文件。 |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_1)(Stream, Stream, CertificateHolder, SignOptions) | 使用给定的符号源文档[`CertificateHolder`](../certificateholder/)和[`SignOptions`](../signoptions/) 带有数字签名并将签名文档写入目标流。 |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_3)(string, string, CertificateHolder, SignOptions) | 使用给定的符号源文档[`CertificateHolder`](../certificateholder/)和[`SignOptions`](../signoptions/) 带有数字签名并将签名文档写入目标文件。 |

### 评论

由于数字签名适用于文件内容而不是文档对象模型，因此这些方法被放入一个单独的类中。

支持的格式是Doc和Docx.

### 例子

演示如何从数字签名文档加载签名。

```csharp
// 有两种方法可以使用 DigitalSignatureUtil 类加载签名文档的数字签名集合。
// 1 - 从本地文件系统文件名的文档加载：
DigitalSignatureCollection digitalSignatures = 
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

// 如果这个集合是非空的，那么我们可以验证该文档是数字签名的。
Assert.AreEqual(1, digitalSignatures.Count);

// 2 - 从 FileStream 中的文档加载：
using (Stream stream = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    digitalSignatures = DigitalSignatureUtil.LoadSignatures(stream);
    Assert.AreEqual(1, digitalSignatures.Count);
}
```

演示如何从数字签名文档中删除数字签名。

```csharp
// 使用 DigitalSignatureUtil 类去除数字签名有两种方式
// 通过将未签名的副本保存在本地文件系统的其他位置来从已签名的文档中提取。
// 1 - 通过文件名字符串确定签名文档和未签名副本的位置：
DigitalSignatureUtil.RemoveAllSignatures(MyDir + "Digitally signed.docx",
    ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx");

// 2 - 通过文件流确定签名文档和未签名副本的位置：
using (Stream streamIn = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx", FileMode.Create))
    {
        DigitalSignatureUtil.RemoveAllSignatures(streamIn, streamOut);
    }
}

// 验证我们的两个输出文档都没有数字签名。
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx"), Is.Empty);
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx"), Is.Empty);
```

### 也可以看看

* 命名空间 [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* 部件 [Aspose.Words](../../)


