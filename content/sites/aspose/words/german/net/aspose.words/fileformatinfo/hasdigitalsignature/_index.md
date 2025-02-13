---
title: FileFormatInfo.HasDigitalSignature
second_title: Aspose.Words für .NET-API-Referenz
description: FileFormatInfo eigendom. Gibt wahr zurück wenn dieses Dokument eine digitale Signatur enthält. Diese Eigenschaft informiert lediglich darüber dass eine digitale Signatur auf einem Dokument vorhanden ist gibt aber nicht an ob die Signatur gültig ist oder nicht.
type: docs
weight: 20
url: /de/net/aspose.words/fileformatinfo/hasdigitalsignature/
---
## FileFormatInfo.HasDigitalSignature property

Gibt wahr zurück, wenn dieses Dokument eine digitale Signatur enthält. Diese Eigenschaft informiert lediglich darüber, dass eine digitale Signatur auf einem Dokument vorhanden ist, gibt aber nicht an, ob die Signatur gültig ist oder nicht.

```csharp
public bool HasDigitalSignature { get; }
```

### Bemerkungen

Diese Eigenschaft hilft Ihnen dabei, digital signierte Dokumente von nicht signierten Dokumenten zu trennen. Wenn Sie Aspose.Words verwenden, um ein digital signiertes Dokument zu ändern und zu speichern, geht die digitale Signatur verloren. Dies ist beabsichtigt, da eine digitale Signatur vorhanden ist, um die Authentizität eines Dokuments zu schützen. Mit dieser Eigenschaft können Sie digital signierte Dokumente erkennen, bevor Sie sie wie normale -Dokumente verarbeiten, und Maßnahmen ergreifen, um den Verlust der digitalen Signatur zu vermeiden, z. B. den Benutzer benachrichtigen.

### Beispiele

Zeigt, wie die FileFormatUtil-Klasse verwendet wird, um das Dokumentformat und das Vorhandensein digitaler Signaturen zu erkennen.

```csharp
// Verwenden Sie eine FileFormatInfo-Instanz, um zu überprüfen, ob ein Dokument nicht digital signiert ist.
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.docx");

Assert.AreEqual(".docx", FileFormatUtil.LoadFormatToExtension(info.LoadFormat));
Assert.False(info.HasDigitalSignature);

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "File.DetectDigitalSignatures.docx",
    certificateHolder, new SignOptions() { SignTime = DateTime.Now });

// Verwenden Sie eine neue FileFormatInstance, um zu bestätigen, dass sie signiert ist.
info = FileFormatUtil.DetectFileFormat(ArtifactsDir + "File.DetectDigitalSignatures.docx");

Assert.True(info.HasDigitalSignature);

// Wir können die Signaturen eines signierten Dokuments in einer Sammlung wie dieser laden und darauf zugreifen.
Assert.AreEqual(1, DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "File.DetectDigitalSignatures.docx").Count);
```

### Siehe auch

* class [FileFormatInfo](../)
* namensraum [Aspose.Words](../../fileformatinfo/)
* Montage [Aspose.Words](../../../)


