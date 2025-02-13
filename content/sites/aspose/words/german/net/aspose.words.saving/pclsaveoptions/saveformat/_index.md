---
title: PclSaveOptions.SaveFormat
second_title: Aspose.Words für .NET-API-Referenz
description: PclSaveOptions eigendom. Gibt das Format an in dem das Dokument gespeichert wird wenn dieses Speicheroptionsobjekt verwendet wird. Kann nur seinPcl .
type: docs
weight: 40
url: /de/net/aspose.words.saving/pclsaveoptions/saveformat/
---
## PclSaveOptions.SaveFormat property

Gibt das Format an, in dem das Dokument gespeichert wird, wenn dieses Speicheroptionsobjekt verwendet wird. Kann nur seinPcl .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

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

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [PclSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pclsaveoptions/)
* Montage [Aspose.Words](../../../)


