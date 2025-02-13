---
title: PdfSaveOptions.EncryptionDetails
second_title: Aspose.Words per .NET API Reference
description: PdfSaveOptions proprietà. Ottiene o imposta i dettagli per la crittografia del documento PDF di output.
type: docs
weight: 110
url: /it/net/aspose.words.saving/pdfsaveoptions/encryptiondetails/
---
## PdfSaveOptions.EncryptionDetails property

Ottiene o imposta i dettagli per la crittografia del documento PDF di output.

```csharp
public PdfEncryptionDetails EncryptionDetails { get; set; }
```

### Osservazioni

Il valore predefinito è null e il documento di output non verrà crittografato. Quando questa proprietà è impostata su un valore valido[`PdfEncryptionDetails`](../../pdfencryptiondetails/) oggetto, , il documento PDF di output verrà crittografato.

L'algoritmo di crittografia AES-128 viene utilizzato durante il salvataggio in conformità basata su PDF 1.7 (incluso PDF/UA-1). L'algoritmo di crittografia AES-256 viene utilizzato durante il salvataggio in conformità basata su PDF 2.0.

La crittografia è vietata dalla conformità PDF/A. Questa opzione verrà ignorata durante il salvataggio in PDF/A.

ContentCopyForAccessibilityl'autorizzazione è richiesta da PDF/UA compliance se il documento di output è crittografato. Questa autorizzazione verrà utilizzata automaticamente durante il salvataggio in PDF/UA.

ContentCopyForAccessibility l'autorizzazione è obsoleta nel formato PDF 2.0. Questa autorizzazione verrà ignorata durante il salvataggio in PDF 2.0.

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

* class [PdfEncryptionDetails](../../pdfencryptiondetails/)
* class [PdfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfsaveoptions/)
* assemblea [Aspose.Words](../../../)


