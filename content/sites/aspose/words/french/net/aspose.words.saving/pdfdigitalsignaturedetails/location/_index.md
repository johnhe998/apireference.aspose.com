---
title: PdfDigitalSignatureDetails.Location
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfDigitalSignatureDetails propriété. Obtient ou définit lemplacement de la signature.
type: docs
weight: 40
url: /fr/net/aspose.words.saving/pdfdigitalsignaturedetails/location/
---
## PdfDigitalSignatureDetails.Location property

Obtient ou définit l'emplacement de la signature.

```csharp
public string Location { get; set; }
```

### Remarques

La valeur par défaut est nulle.

### Exemples

Montre comment signer un document PDF généré.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Configurez l'objet "DigitalSignatureDetails" de l'objet "SaveOptions" pour
// signe numériquement le document tel que nous le rendons avec la méthode "Save".
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### Voir également

* class [PdfDigitalSignatureDetails](../)
* espace de noms [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* Assemblée [Aspose.Words](../../../)


