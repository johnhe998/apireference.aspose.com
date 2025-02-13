---
title: SignOptions.DecryptionPassword
second_title: Справочник по API Aspose.Words для .NET
description: SignOptions свойство. Пароль для расшифровки исходного документа. Значение по умолчанию пустой строки Empty .
type: docs
weight: 30
url: /ru/net/aspose.words.digitalsignatures/signoptions/decryptionpassword/
---
## SignOptions.DecryptionPassword property

Пароль для расшифровки исходного документа. Значение по умолчанию: **пустой строки** (Empty ).

```csharp
public string DecryptionPassword { get; set; }
```

### Примечания

Если документ OOXML зашифрован, вы должны указать пароль дешифрования для расшифровки исходного документа перед тем, как он будет подписан. Это не требуется для документов в двоичном формате DOC.

### Примеры

Показывает, как подписать зашифрованный файл документа.

```csharp
// Создайте сертификат X.509 из хранилища PKCS#12, который должен содержать закрытый ключ.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Создайте комментарий, дату и пароль для расшифровки, которые будут применяться с нашей новой цифровой подписью.
SignOptions signOptions = new SignOptions
{
    Comments = "Comment",
    SignTime = DateTime.Now,
    DecryptionPassword = "docPassword"
};

// Установите имя локального системного файла для неподписанного входного документа и имя выходного файла для его новой копии с цифровой подписью.
string inputFileName = MyDir + "Encrypted.docx";
string outputFileName = ArtifactsDir + "DigitalSignatureUtil.DecryptionPassword.docx";

DigitalSignatureUtil.Sign(inputFileName, outputFileName, certificateHolder, signOptions);
```

### Смотрите также

* class [SignOptions](../)
* пространство имен [Aspose.Words.DigitalSignatures](../../signoptions/)
* сборка [Aspose.Words](../../../)


