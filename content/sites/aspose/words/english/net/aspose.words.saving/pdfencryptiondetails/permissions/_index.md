---
title: PdfEncryptionDetails.Permissions
linktitle: Permissions
articleTitle: Permissions
second_title: Aspose.Words for .NET
description: PdfEncryptionDetails Permissions property. Specifies the operations that are allowed to a user on an encrypted PDF document. The default value is DisallowAll in C#.
type: docs
weight: 30
url: /net/aspose.words.saving/pdfencryptiondetails/permissions/
---
## PdfEncryptionDetails.Permissions property

Specifies the operations that are allowed to a user on an encrypted PDF document. The default value is DisallowAll.

```csharp
public PdfPermissions Permissions { get; set; }
```

## Examples

Shows how to set permissions on a saved PDF document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// Start by disallowing all permissions.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// Extend permissions to allow the editing of annotations.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// Create a "PdfSaveOptions" object that we can pass to the document's "Save" method
// to modify how that method converts the document to .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Enable encryption via the "EncryptionDetails" property.
saveOptions.EncryptionDetails = encryptionDetails;

// When we open this document, we will need to provide the password before accessing its contents.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### See Also

* enum [PdfPermissions](../../pdfpermissions/)
* class [PdfEncryptionDetails](../)
* namespace [Aspose.Words.Saving](../../../aspose.words.saving/)
* assembly [Aspose.Words](../../../)
