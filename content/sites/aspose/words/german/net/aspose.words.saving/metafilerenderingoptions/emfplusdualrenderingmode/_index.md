---
title: MetafileRenderingOptions.EmfPlusDualRenderingMode
second_title: Aspose.Words für .NET-API-Referenz
description: MetafileRenderingOptions eigendom. Ruft einen Wert ab oder legt einen Wert fest der bestimmt wie EMF DualMetadateien gerendert werden sollen.
type: docs
weight: 20
url: /de/net/aspose.words.saving/metafilerenderingoptions/emfplusdualrenderingmode/
---
## MetafileRenderingOptions.EmfPlusDualRenderingMode property

Ruft einen Wert ab oder legt einen Wert fest, der bestimmt, wie EMF+ Dual-Metadateien gerendert werden sollen.

```csharp
public EmfPlusDualRenderingMode EmfPlusDualRenderingMode { get; set; }
```

### Bemerkungen

EMF+ Dual-Metadateien enthalten sowohl EMF+- als auch EMF-Teile. MS Word und GDI+ rendern immer den EMF+-Teil. Aspose.Words unterstützt derzeit nicht alle EMF+-Datensätze vollständig und in einigen Fällen sieht das Rendern des Ergebnisses des EMF-Teils besser aus als das Rendern des Ergebnisses des EMF+-Teils.

Diese Option wird nur verwendet, wenn die Metadatei als Vektorgrafik gerendert wird. Wenn die Metadatei in Bitmap gerendert wird, wird immer der EMF+-Teil verwendet.

Der Standardwert istEmfPlusWithFallback.

### Beispiele

Zeigt, wie erweiterte Windows-Metadatei-bezogene Rendering-Optionen beim Speichern in PDF konfiguriert werden.

```csharp
Document doc = new Document(MyDir + "EMF.docx");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Setzen Sie die Eigenschaft "EmfPlusDualRenderingMode" auf "EmfPlusDualRenderingMode.Emf"
// um nur den EMF-Teil einer dualen EMF+-Metadatei zu rendern.
// Legen Sie die Eigenschaft "EmfPlusDualRenderingMode" auf "EmfPlusDualRenderingMode.EmfPlus" fest
// um den EMF+-Teil einer dualen EMF+-Metadatei zu rendern.
// Setzen Sie die Eigenschaft "EmfPlusDualRenderingMode" auf "EmfPlusDualRenderingMode.EmfPlusWithFallback"
// zum Rendern des EMF+-Teils einer dualen EMF+-Metadatei, wenn alle EMF+-Einträge unterstützt werden.
// Andernfalls rendert Aspose.Words den EMF-Teil.
saveOptions.MetafileRenderingOptions.EmfPlusDualRenderingMode = renderingMode;

// Legen Sie die Eigenschaft "UseEmfEmbeddedToWmf" auf "true" fest, um eingebettete EMF-Daten zu rendern
// für Metadateien, die wir als Vektorgrafiken rendern können.
saveOptions.MetafileRenderingOptions.UseEmfEmbeddedToWmf = true;

doc.Save(ArtifactsDir + "PdfSaveOptions.RenderMetafile.pdf", saveOptions);
```

### Siehe auch

* enum [EmfPlusDualRenderingMode](../../emfplusdualrenderingmode/)
* class [MetafileRenderingOptions](../)
* namensraum [Aspose.Words.Saving](../../metafilerenderingoptions/)
* Montage [Aspose.Words](../../../)


