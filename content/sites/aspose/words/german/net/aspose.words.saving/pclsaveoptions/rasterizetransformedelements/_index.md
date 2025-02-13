---
title: PclSaveOptions.RasterizeTransformedElements
second_title: Aspose.Words für .NET-API-Referenz
description: PclSaveOptions eigendom. Ruft einen Wert ab oder legt ihn fest der bestimmt ob komplexe transformierte Elemente vor dem Speichern in ein PCLDokument gerastert werden sollen. Standard istStimmt .
type: docs
weight: 30
url: /de/net/aspose.words.saving/pclsaveoptions/rasterizetransformedelements/
---
## PclSaveOptions.RasterizeTransformedElements property

Ruft einen Wert ab oder legt ihn fest, der bestimmt, ob komplexe transformierte Elemente vor dem Speichern in ein PCL-Dokument gerastert werden sollen. Standard ist`Stimmt` .

```csharp
public bool RasterizeTransformedElements { get; set; }
```

### Bemerkungen

PCL unterstützt einige Transformationen nicht, die von Aspose Words verwendet werden. ZB gedrehte, schiefe Bilder und Texturpinsel. Um solche Elemente richtig zu rendern, wird ein Rasterisierungsprozess verwendet, dh Speichern im Bild und Zuschneiden. Dieser Prozess kann zusätzliche Zeit und Speicherplatz beanspruchen. Wenn das Flag auf gesetzt ist`FALSCH` einige Inhalte in der Ausgabe können im Vergleich zum Quelldokument unterschiedlich sein.

### Beispiele

Zeigt, wie komplexe Elemente beim Speichern eines Dokuments in PCL gerastert werden.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### Siehe auch

* class [PclSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pclsaveoptions/)
* Montage [Aspose.Words](../../../)


