---
title: PdfEncryptionDetails.OwnerPassword
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfEncryptionDetails propriété. Spécifie le mot de passe du propriétaire du document PDF crypté.
type: docs
weight: 20
url: /fr/net/aspose.words.saving/pdfencryptiondetails/ownerpassword/
---
## PdfEncryptionDetails.OwnerPassword property

Spécifie le mot de passe du propriétaire du document PDF crypté.

```csharp
public string OwnerPassword { get; set; }
```

### Remarques

Le mot de passe propriétaire permet à l'utilisateur d'ouvrir un document PDF crypté sans aucune restriction d'accès spécifiée dans[`Permissions`](../permissions/).

Le mot de passe propriétaire ne peut pas être le même que le mot de passe utilisateur.

### Exemples

Montre comment définir des autorisations sur un document PDF enregistré.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// Commencez par interdire toutes les autorisations.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// Étend les autorisations pour permettre la modification des annotations.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Activer le chiffrement via la propriété "EncryptionDetails".
saveOptions.EncryptionDetails = encryptionDetails;

// Lorsque nous ouvrons ce document, nous devrons fournir le mot de passe avant d'accéder à son contenu.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### Voir également

* class [PdfEncryptionDetails](../)
* espace de noms [Aspose.Words.Saving](../../pdfencryptiondetails/)
* Assemblée [Aspose.Words](../../../)


