---
title: DigitalSignature.CertificateHolder
second_title: Aspose.Words für .NET-API-Referenz
description: DigitalSignature eigendom. Gibt das Zertifikatsinhaberobjekt zurück das das Zertifikat enthält das zum Signieren des Dokuments verwendet wurde.
type: docs
weight: 10
url: /de/net/aspose.words.digitalsignatures/digitalsignature/certificateholder/
---
## DigitalSignature.CertificateHolder property

Gibt das Zertifikatsinhaberobjekt zurück, das das Zertifikat enthält, das zum Signieren des Dokuments verwendet wurde.

```csharp
public CertificateHolder CertificateHolder { get; }
```

### Beispiele

Zeigt, wie Dokumente mit X.509-Zertifikaten signiert werden.

```csharp
// Sicherstellen, dass ein Dokument nicht signiert ist.
Assert.False(FileFormatUtil.DetectFileFormat(MyDir + "Document.docx").HasDigitalSignature);

// Erstellen Sie ein CertificateHolder-Objekt aus einer PKCS12-Datei, mit der wir das Dokument signieren.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);

// Es gibt zwei Möglichkeiten, eine signierte Kopie eines Dokuments im lokalen Dateisystem zu speichern:
// 1 - Kennzeichnen eines Dokuments durch einen lokalen Systemdateinamen und Speichern einer signierten Kopie an einem Ort, der durch einen anderen Dateinamen angegeben ist.
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "Document.DigitalSignature.docx", 
    certificateHolder, new SignOptions() { SignTime = DateTime.Now } );

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// 2 - Nehmen Sie ein Dokument aus einem Stream und speichern Sie eine signierte Kopie in einem anderen Stream.
using (FileStream inDoc = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (FileStream outDoc = new FileStream(ArtifactsDir + "Document.DigitalSignature.docx", FileMode.Create))
    {
        DigitalSignatureUtil.Sign(inDoc, outDoc, certificateHolder);
    }
}

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// Bitte überprüfen Sie, ob alle digitalen Signaturen des Dokuments gültig sind, und überprüfen Sie deren Details.
Document signedDoc = new Document(ArtifactsDir + "Document.DigitalSignature.docx");
DigitalSignatureCollection digitalSignatureCollection = signedDoc.DigitalSignatures;

Assert.True(digitalSignatureCollection.IsValid);
Assert.AreEqual(1, digitalSignatureCollection.Count);
Assert.AreEqual(DigitalSignatureType.XmlDsig, digitalSignatureCollection[0].SignatureType);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].IssuerName);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].SubjectName);
```

### Siehe auch

* class [CertificateHolder](../../certificateholder/)
* class [DigitalSignature](../)
* namensraum [Aspose.Words.DigitalSignatures](../../digitalsignature/)
* Montage [Aspose.Words](../../../)


