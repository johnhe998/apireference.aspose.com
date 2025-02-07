---
title: PdfEncryptionDetails.PdfEncryptionDetails
second_title: Aspose.Words per .NET API Reference
description: PdfEncryptionDetails costruttore. Inizializza unistanza di questa classe.
type: docs
weight: 10
url: /it/net/aspose.words.saving/pdfencryptiondetails/pdfencryptiondetails/
---
## PdfEncryptionDetails constructor

Inizializza un'istanza di questa classe.

```csharp
public PdfEncryptionDetails(string userPassword, string ownerPassword)
```

### Esempi

Mostra come impostare le autorizzazioni su un documento PDF salvato.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// Inizia negando tutte le autorizzazioni.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// Estendi i permessi per consentire la modifica delle annotazioni.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Abilita la crittografia tramite la proprietà "EncryptionDetails".
saveOptions.EncryptionDetails = encryptionDetails;

// Quando apriremo questo documento, dovremo fornire la password prima di accedere al suo contenuto.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### Guarda anche

* class [PdfEncryptionDetails](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfencryptiondetails/)
* assemblea [Aspose.Words](../../../)


