---
title: DigitalSignature.SubjectName
second_title: Справочник по API Aspose.Words для .NET
description: DigitalSignature свойство. Возвращает различающееся имя субъекта сертификата который использовался для подписи документа.
type: docs
weight: 70
url: /ru/net/aspose.words.digitalsignatures/digitalsignature/subjectname/
---
## DigitalSignature.SubjectName property

Возвращает различающееся имя субъекта сертификата, который использовался для подписи документа.

```csharp
public string SubjectName { get; }
```

### Примеры

Показывает, как подписывать документы сертификатами X.509.

```csharp
// Проверяем, что документ не подписан.
Assert.False(FileFormatUtil.DetectFileFormat(MyDir + "Document.docx").HasDigitalSignature);

// Создадим объект CertificateHolder из файла PKCS12, который мы будем использовать для подписи документа.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);

// Есть два способа сохранить подписанную копию документа в локальную файловую систему:
// 1 - Назначить документ именем локального системного файла и сохранить подписанную копию в месте, указанном другим именем файла.
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "Document.DigitalSignature.docx", 
    certificateHolder, new SignOptions() { SignTime = DateTime.Now } );

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// 2 - Взять документ из потока и сохранить подписанную копию в другой поток.
using (FileStream inDoc = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (FileStream outDoc = new FileStream(ArtifactsDir + "Document.DigitalSignature.docx", FileMode.Create))
    {
        DigitalSignatureUtil.Sign(inDoc, outDoc, certificateHolder);
    }
}

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// Убедитесь, что все цифровые подписи документа действительны, и проверьте их данные.
Document signedDoc = new Document(ArtifactsDir + "Document.DigitalSignature.docx");
DigitalSignatureCollection digitalSignatureCollection = signedDoc.DigitalSignatures;

Assert.True(digitalSignatureCollection.IsValid);
Assert.AreEqual(1, digitalSignatureCollection.Count);
Assert.AreEqual(DigitalSignatureType.XmlDsig, digitalSignatureCollection[0].SignatureType);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].IssuerName);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].SubjectName);
```

### Смотрите также

* class [DigitalSignature](../)
* пространство имен [Aspose.Words.DigitalSignatures](../../digitalsignature/)
* сборка [Aspose.Words](../../../)


