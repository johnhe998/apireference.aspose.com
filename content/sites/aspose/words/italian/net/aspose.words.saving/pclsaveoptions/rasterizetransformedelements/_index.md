---
title: PclSaveOptions.RasterizeTransformedElements
second_title: Aspose.Words per .NET API Reference
description: PclSaveOptions proprietà. Ottiene o imposta un valore che determina se gli elementi trasformati complessi devono essere rasterizzati o meno prima del salvataggio nel documento PCL. Limpostazione predefinita èVERO .
type: docs
weight: 30
url: /it/net/aspose.words.saving/pclsaveoptions/rasterizetransformedelements/
---
## PclSaveOptions.RasterizeTransformedElements property

Ottiene o imposta un valore che determina se gli elementi trasformati complessi devono essere rasterizzati o meno prima del salvataggio nel documento PCL. L'impostazione predefinita è`VERO` .

```csharp
public bool RasterizeTransformedElements { get; set; }
```

### Osservazioni

PCL non supporta alcuni tipi di trasformazioni utilizzate da Aspose Words. Ad esempio immagini ruotate, inclinate e pennelli texture. Per eseguire correttamente il rendering di tali elementi viene utilizzato il processo di rasterizzazione, ovvero il salvataggio nell'immagine e il ritaglio. Questo processo può richiedere tempo e memoria aggiuntivi. Se flag è impostato su`falso` alcuni contenuti nell'output potrebbero essere diversi rispetto al documento di origine.

### Esempi

Mostra come rasterizzare elementi complessi durante il salvataggio di un documento in PCL.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### Guarda anche

* class [PclSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pclsaveoptions/)
* assemblea [Aspose.Words](../../../)


