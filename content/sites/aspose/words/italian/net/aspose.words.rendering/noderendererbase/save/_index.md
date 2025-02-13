---
title: NodeRendererBase.Save
second_title: Aspose.Words per .NET API Reference
description: NodeRendererBase metodo. Rende la forma in unimmagine e salva in un file.
type: docs
weight: 90
url: /it/net/aspose.words.rendering/noderendererbase/save/
---
## Save(string, ImageSaveOptions) {#save_1}

Rende la forma in un'immagine e salva in un file.

```csharp
public void Save(string fileName, ImageSaveOptions saveOptions)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| fileName | String | Il nome del file immagine. Se esiste già un file con il nome specificato, il file esistente viene sovrascritto. |
| saveOptions | ImageSaveOptions | Specifica le opzioni che controllano la modalità di rendering e salvataggio della forma. Può essere nullo. |

### Esempi

Mostra come eseguire il rendering di un oggetto Office Math in un file immagine nel file system locale.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// Crea un oggetto "ImageSaveOptions" da passare al metodo "Save" del renderer del nodo per modificarlo
// come esegue il rendering del nodo OfficeMath in un'immagine.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// Imposta la proprietà "Scale" su 5 per rendere l'oggetto cinque volte la sua dimensione originale.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### Guarda anche

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* spazio dei nomi [Aspose.Words.Rendering](../../noderendererbase/)
* assemblea [Aspose.Words](../../../)

---

## Save(Stream, ImageSaveOptions) {#save}

Rende la forma in un'immagine e salva in un flusso.

```csharp
public void Save(Stream stream, ImageSaveOptions saveOptions)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| stream | Stream | Il flusso in cui salvare l'immagine della forma. |
| saveOptions | ImageSaveOptions | Specifica le opzioni che controllano la modalità di rendering e salvataggio della forma. Può essere null. Se è nullo, l'immagine verrà salvata nel formato PNG. |

### Esempi

Mostra come utilizzare un renderer di forme per esportare forme in file nel file system locale.

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// Ci sono 7 forme nel documento, inclusa una forma di gruppo con 2 forme figlio.
// Rendering di ogni forma in un file immagine nel file system locale
// ignorando le forme di gruppo poiché non hanno aspetto.
// Questo produrrà 6 file immagine.
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### Guarda anche

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* spazio dei nomi [Aspose.Words.Rendering](../../noderendererbase/)
* assemblea [Aspose.Words](../../../)


