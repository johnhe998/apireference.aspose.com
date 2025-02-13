---
title: PdfSaveOptions.CustomPropertiesExport
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Ruft oder setzt einen Wert der den Weg bestimmtCustomDocumentProperties werden in eine PDFDatei exportiert.
type: docs
weight: 50
url: /de/net/aspose.words.saving/pdfsaveoptions/custompropertiesexport/
---
## PdfSaveOptions.CustomPropertiesExport property

Ruft oder setzt einen Wert, der den Weg bestimmt[`CustomDocumentProperties`](../../../aspose.words/document/customdocumentproperties/) werden in eine PDF-Datei exportiert.

```csharp
public PdfCustomPropertiesExport CustomPropertiesExport { get; set; }
```

### Bemerkungen

Standardwert istNone.

Metadata Wert wird beim Speichern in PDF/A nicht unterstützt. Standard wird stattdessen für PDF/A-1 und PDF/A-2 und verwendetNone für PDF/A-4.

Standard Wert wird beim Speichern in PDF 2.0. nicht unterstütztMetadata wird stattdessen verwendet.

### Beispiele

Zeigt, wie benutzerdefinierte Eigenschaften exportiert werden, während ein Dokument in PDF konvertiert wird.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("Company", "My value");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Legen Sie die Eigenschaft "CustomPropertiesExport" auf "PdfCustomPropertiesExport.None" fest, um sie zu verwerfen
 // benutzerdefinierte Dokumenteigenschaften, während wir das Dokument als .PDF speichern.
// Setzen Sie die Eigenschaft "CustomPropertiesExport" auf "PdfCustomPropertiesExport.Standard"
// um benutzerdefinierte Eigenschaften im ausgegebenen PDF-Dokument beizubehalten.
// Setzen Sie die Eigenschaft "CustomPropertiesExport" auf "PdfCustomPropertiesExport.Metadata"
// um benutzerdefinierte Eigenschaften in einem XMP-Paket beizubehalten.
options.CustomPropertiesExport = pdfCustomPropertiesExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.CustomPropertiesExport.pdf", options);
```

### Siehe auch

* enum [PdfCustomPropertiesExport](../../pdfcustompropertiesexport/)
* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


