---
title: PdfSaveOptions.EncryptionDetails
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Ruft die Details zum Verschlüsseln des ausgegebenen PDFDokuments ab oder legt sie fest.
type: docs
weight: 110
url: /de/net/aspose.words.saving/pdfsaveoptions/encryptiondetails/
---
## PdfSaveOptions.EncryptionDetails property

Ruft die Details zum Verschlüsseln des ausgegebenen PDF-Dokuments ab oder legt sie fest.

```csharp
public PdfEncryptionDetails EncryptionDetails { get; set; }
```

### Bemerkungen

Der Standardwert ist null und das Ausgabedokument wird nicht verschlüsselt. Wenn diese Eigenschaft auf gültig gesetzt ist[`PdfEncryptionDetails`](../../pdfencryptiondetails/) object, , dann wird das ausgegebene PDF-Dokument verschlüsselt.

Der AES-128-Verschlüsselungsalgorithmus wird beim Speichern in PDF 1.7-basierter Kompatibilität (einschließlich PDF/UA-1) verwendet. Der AES-256-Verschlüsselungsalgorithmus wird verwendet, wenn in PDF 2.0-basierter Kompatibilität gespeichert wird.

Die Verschlüsselung ist durch die PDF/A-Konformität verboten. Diese Option wird beim Speichern in PDF/A ignoriert.

ContentCopyForAccessibilityDie Berechtigung ist von PDF/UA compliance erforderlich, wenn das Ausgabedokument verschlüsselt ist. Diese Berechtigung wird automatisch beim Speichern in PDF/UA verwendet.

ContentCopyForAccessibility Berechtigung ist im PDF 2.0-Format veraltet. Diese Berechtigung wird beim Speichern in PDF 2.0 ignoriert.

### Beispiele

Zeigt, wie Berechtigungen für ein gespeichertes PDF-Dokument festgelegt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// Beginnen Sie damit, alle Berechtigungen zu verweigern.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// Berechtigungen erweitern, um die Bearbeitung von Anmerkungen zu ermöglichen.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Verschlüsselung über die Eigenschaft "EncryptionDetails" aktivieren.
saveOptions.EncryptionDetails = encryptionDetails;

// Wenn wir dieses Dokument öffnen, müssen wir das Passwort angeben, bevor wir auf seinen Inhalt zugreifen können.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### Siehe auch

* class [PdfEncryptionDetails](../../pdfencryptiondetails/)
* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


