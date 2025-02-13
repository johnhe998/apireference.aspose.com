---
title: ImageSaveOptions.MetafileRenderingOptions
second_title: Aspose.Words per .NET API Reference
description: ImageSaveOptions proprietà. Consente di specificare come vengono trattati i metafile nelloutput renderizzato.
type: docs
weight: 80
url: /it/net/aspose.words.saving/imagesaveoptions/metafilerenderingoptions/
---
## ImageSaveOptions.MetafileRenderingOptions property

Consente di specificare come vengono trattati i metafile nell'output renderizzato.

```csharp
public MetafileRenderingOptions MetafileRenderingOptions { get; }
```

### Osservazioni

quandoVector è specificato, Aspose.Words esegue il rendering del metafile in grafica vettoriale utilizzando prima il proprio motore di rendering del metafile, quindi esegue il rendering della grafica vettoriale nell'immagine.

quandoBitmap viene specificato, Aspose.Words esegue il rendering del metafile direttamente nell'immagine utilizzando il motore di rendering del metafile GDI+.

Il motore di rendering di metafile GDI+ funziona più velocemente, supporta quasi tutte le funzionalità di metafile ma su risoluzioni basse può produrre risultati incoerenti rispetto al resto della grafica vettoriale (soprattutto per il testo) sulla pagina. Il motore di rendering dei metafile Aspose.Words produrrà risultati più coerenti anche a basse risoluzioni, ma funziona più lentamente e potrebbe rendere inaccurati metafile complessi.

Il valore predefinito per[`MetafileRenderingMode`](../../metafilerenderingmode/) èBitmap.

### Esempi

Mostra come impostare la modalità di rendering durante il salvataggio di documenti con immagini di Windows Metafile in altri formati di immagine.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(Image.FromFile(ImageDir + "Windows MetaFile.wmf"));

// Quando salviamo il documento come immagine, possiamo passare un oggetto SaveOptions a
// determina come l'operazione di salvataggio elaborerà i metafile di Windows nel documento.
// Se impostiamo la proprietà "RenderingMode" su "MetafileRenderingMode.Vector",
// o "MetafileRenderingMode.VectorWithFallback", renderemo tutti i metafile come grafica vettoriale.
// Se impostiamo la proprietà "RenderingMode" su "MetafileRenderingMode.Bitmap", renderemo tutti i metafile come bitmap.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
options.MetafileRenderingOptions.RenderingMode = metafileRenderingMode;

doc.Save(ArtifactsDir + "ImageSaveOptions.WindowsMetaFile.png", options);
```

### Guarda anche

* class [MetafileRenderingOptions](../../metafilerenderingoptions/)
* class [ImageSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../imagesaveoptions/)
* assemblea [Aspose.Words](../../../)


