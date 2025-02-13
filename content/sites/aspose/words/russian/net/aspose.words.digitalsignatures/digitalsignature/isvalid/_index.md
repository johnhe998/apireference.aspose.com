---
title: DigitalSignature.IsValid
second_title: Справочник по API Aspose.Words для .NET
description: DigitalSignature свойство. Возвращает true если эта цифровая подпись действительна и документ не был подделан.
type: docs
weight: 40
url: /ru/net/aspose.words.digitalsignatures/digitalsignature/isvalid/
---
## DigitalSignature.IsValid property

Возвращает true, если эта цифровая подпись действительна и документ не был подделан.

```csharp
public bool IsValid { get; }
```

### Примеры

Показывает, как проверять и отображать информацию о каждой подписи в документе.

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

### Смотрите также

* class [DigitalSignature](../)
* пространство имен [Aspose.Words.DigitalSignatures](../../digitalsignature/)
* сборка [Aspose.Words](../../../)


