---
title: Class DigitalSignature
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.DigitalSignatures.DigitalSignature сорт. Представляет цифровую подпись документа и результат ее проверки.
type: docs
weight: 370
url: /ru/net/aspose.words.digitalsignatures/digitalsignature/
---
## DigitalSignature class

Представляет цифровую подпись документа и результат ее проверки.

```csharp
public class DigitalSignature
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [CertificateHolder](../../aspose.words.digitalsignatures/digitalsignature/certificateholder/) { get; } | Возвращает объект держателя сертификата, содержащий сертификат, который использовался для подписи документа. |
| [Comments](../../aspose.words.digitalsignatures/digitalsignature/comments/) { get; } | Получает комментарий к цели подписания. |
| [IssuerName](../../aspose.words.digitalsignatures/digitalsignature/issuername/) { get; } | Возвращает различающееся имя субъекта сертификата isuuer. |
| [IsValid](../../aspose.words.digitalsignatures/digitalsignature/isvalid/) { get; } | Возвращает true, если эта цифровая подпись действительна и документ не был подделан. |
| [SignatureType](../../aspose.words.digitalsignatures/digitalsignature/signaturetype/) { get; } | Получает тип цифровой подписи. |
| [SignTime](../../aspose.words.digitalsignatures/digitalsignature/signtime/) { get; } | Получает время подписания документа. |
| [SubjectName](../../aspose.words.digitalsignatures/digitalsignature/subjectname/) { get; } | Возвращает различающееся имя субъекта сертификата, который использовался для подписи документа. |

## Методы

| Имя | Описание |
| --- | --- |
| override [ToString](../../aspose.words.digitalsignatures/digitalsignature/tostring/)() | Возвращает удобную для пользователя строку, отображающую значение этого объекта. |

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

* пространство имен [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* сборка [Aspose.Words](../../)


