---
title: DocSaveOptions.AlwaysCompressMetafiles
second_title: Aspose.Words für .NET-API-Referenz
description: DocSaveOptions eigendom. WannFALSCH  kleine Metadateien werden aus Leistungsgründen nicht komprimiert. Standardwert ist Stimmt  werden alle Metadateien unabhängig von ihrer Größe komprimiert.
type: docs
weight: 20
url: /de/net/aspose.words.saving/docsaveoptions/alwayscompressmetafiles/
---
## DocSaveOptions.AlwaysCompressMetafiles property

Wann`FALSCH` , kleine Metadateien werden aus Leistungsgründen nicht komprimiert. Standardwert ist **Stimmt** , werden alle Metadateien unabhängig von ihrer Größe komprimiert.

```csharp
public bool AlwaysCompressMetafiles { get; set; }
```

### Beispiele

Zeigt, wie die Komprimierung von Metadateien in einem Dokument beim Speichern geändert wird.

```csharp
// Öffnen Sie ein Dokument, das eine Microsoft Equation 3.0-Formel enthält.
Document doc = new Document(MyDir + "Microsoft equation object.docx");

// Wenn wir ein Dokument speichern, werden kleinere Metadateien aus Performancegründen nicht komprimiert.
// Wir können ein Flag in einem SaveOptions-Objekt setzen, um jede Metadatei beim Speichern zu komprimieren.
// Einige Editoren wie LibreOffice können unkomprimierte Metadateien nicht lesen.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.AlwaysCompressMetafiles = compressAllMetafiles;

doc.Save(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx", saveOptions);

if (compressAllMetafiles)
    Assert.That(10000, Is.LessThan(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
else
    Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
```

### Siehe auch

* class [DocSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../docsaveoptions/)
* Montage [Aspose.Words](../../../)


