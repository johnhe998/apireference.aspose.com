---
title: SignOptions.Comments
second_title: Справочник по API Aspose.Words для .NET
description: SignOptions свойство. Задает комментарии к цифровой подписи. Значение по умолчанию пустой строки Empty .
type: docs
weight: 20
url: /ru/net/aspose.words.digitalsignatures/signoptions/comments/
---
## SignOptions.Comments property

Задает комментарии к цифровой подписи. Значение по умолчанию: **пустой строки** (Empty ).

```csharp
public string Comments { get; set; }
```

### Примеры

Показывает, как подписывать документы цифровой подписью.

```csharp
// Создайте сертификат X.509 из хранилища PKCS#12, который должен содержать закрытый ключ.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Создайте комментарий и дату, которые будут применяться с нашей новой цифровой подписью.
SignOptions signOptions = new SignOptions
{
    Comments = "My comment", 
    SignTime = DateTime.Now
};

// Берём неподписанный документ из локальной файловой системы через файловый поток,
// затем создайте его подписанную копию, определяемую именем файла выходного файлового потока.
using (Stream streamIn = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.SignDocument.docx", FileMode.OpenOrCreate))
    {
        DigitalSignatureUtil.Sign(streamIn, streamOut, certificateHolder, signOptions);
    }
}
```

### Смотрите также

* class [SignOptions](../)
* пространство имен [Aspose.Words.DigitalSignatures](../../signoptions/)
* сборка [Aspose.Words](../../../)


