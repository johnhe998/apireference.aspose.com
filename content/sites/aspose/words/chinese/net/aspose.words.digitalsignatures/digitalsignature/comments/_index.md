---
title: DigitalSignature.Comments
second_title: Aspose.Words for .NET API 参考
description: DigitalSignature 财产. 获取签名目的注释
type: docs
weight: 20
url: /zh/net/aspose.words.digitalsignatures/digitalsignature/comments/
---
## DigitalSignature.Comments property

获取签名目的注释。

```csharp
public string Comments { get; }
```

### 例子

演示如何验证和显示有关文档中每个签名的信息。

```csharp
Document doc = new Document(MyDir + "Digitally signed.docx");

foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine($"{(signature.IsValid ? "Valid" : "Invalid")} signature: ");
    Console.WriteLine($"\tReason:\t{signature.Comments}"); 
    Console.WriteLine($"\tType:\t{signature.SignatureType}");
    Console.WriteLine($"\tSign time:\t{signature.SignTime}");
    Console.WriteLine($"\tSubject name:\t{signature.CertificateHolder.Certificate.SubjectName}");
    Console.WriteLine($"\tIssuer name:\t{signature.CertificateHolder.Certificate.IssuerName.Name}");
    Console.WriteLine();
}
```

### 也可以看看

* class [DigitalSignature](../)
* 命名空间 [Aspose.Words.DigitalSignatures](../../digitalsignature/)
* 部件 [Aspose.Words](../../../)


