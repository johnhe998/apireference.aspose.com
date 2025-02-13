---
title: Enum PdfCustomPropertiesExport
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.PdfCustomPropertiesExport opsomming. Gibt den Weg anCustomDocumentProperties werden in eine PDFDatei exportiert.
type: docs
weight: 5140
url: /de/net/aspose.words.saving/pdfcustompropertiesexport/
---
## PdfCustomPropertiesExport enumeration

Gibt den Weg an[`CustomDocumentProperties`](../../aspose.words/document/customdocumentproperties/) werden in eine PDF-Datei exportiert.

```csharp
public enum PdfCustomPropertiesExport
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Es werden keine benutzerdefinierten Eigenschaften exportiert. |
| Standard | `1` | Benutzerdefinierte Eigenschaften werden als Einträge im /Info-Wörterbuch exportiert. |
| Metadata | `2` | Benutzerdefinierte Eigenschaften sind Metadaten. |

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


