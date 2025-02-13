---
title: SaveOptions.MemoryOptimization
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Holt oder legt einen Wert fest der bestimmt ob eine Speicheroptimierung durchgeführt werden soll bevor das Dokument gespeichert wird. Der Standardwert für diese Eigenschaft ist FALSCH .
type: docs
weight: 110
url: /de/net/aspose.words.saving/saveoptions/memoryoptimization/
---
## SaveOptions.MemoryOptimization property

Holt oder legt einen Wert fest, der bestimmt, ob eine Speicheroptimierung durchgeführt werden soll, bevor das Dokument gespeichert wird. Der Standardwert für diese Eigenschaft ist **FALSCH** .

```csharp
public bool MemoryOptimization { get; set; }
```

### Bemerkungen

Wenn Sie diese Option auf „true“ setzen, kann der Speicherverbrauch erheblich verringert werden, während große Dokumente auf Kosten einer langsameren Speicherzeit gespeichert werden.

### Beispiele

Zeigt eine Option zum Optimieren des Speicherverbrauchs beim Rendern großer Dokumente in PDF an.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Pdf);

// Setzen Sie die Eigenschaft „MemoryOptimization“ auf „true“, um den Speicherbedarf beim Speichern großer Dokumente zu verringern
// auf Kosten der Verlängerung der Operationsdauer.
// Setzen Sie die Eigenschaft "MemoryOptimization" auf "false", um das Dokument normal als PDF zu speichern.
saveOptions.MemoryOptimization = memoryOptimization;

doc.Save(ArtifactsDir + "PdfSaveOptions.MemoryOptimization.pdf", saveOptions);
```

### Siehe auch

* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


