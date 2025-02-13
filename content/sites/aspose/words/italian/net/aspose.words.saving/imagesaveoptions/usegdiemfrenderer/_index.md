---
title: ImageSaveOptions.UseGdiEmfRenderer
second_title: Aspose.Words per .NET API Reference
description: ImageSaveOptions proprietà. Ottiene o imposta un valore che determina se utilizzare il renderer di metafile GDI o Aspose.Words durante il salvataggio in EMF.
type: docs
weight: 180
url: /it/net/aspose.words.saving/imagesaveoptions/usegdiemfrenderer/
---
## ImageSaveOptions.UseGdiEmfRenderer property

Ottiene o imposta un valore che determina se utilizzare il renderer di metafile GDI+ o Aspose.Words durante il salvataggio in EMF.

```csharp
public bool UseGdiEmfRenderer { get; set; }
```

### Osservazioni

Se impostato su`VERO`Viene utilizzato il renderer di metafile GDI+. Ad esempio, il contenuto viene scritto nell'oggetto GDI+ graphics e salvato nel metafile.

Se impostato su`falso` Viene utilizzato il renderer di metafile Aspose.Words. Cioè il contenuto viene scritto direttamente nel formato del metafile con Aspose.Words.

Ha effetto solo durante il salvataggio in EMF.

Il salvataggio GDI+ funziona solo su .NET.

Il valore predefinito è`VERO`.

### Esempi

Mostra come scegliere un renderer durante la conversione di un documento in .emf.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            // Quando salviamo il documento come immagine EMF, possiamo passare un oggetto SaveOptions per selezionare un renderer per l'immagine.
            // Se impostiamo il flag "UseGdiEmfRenderer" su "true", Aspose.Words utilizzerà il renderer GDI+.
            // Se impostiamo il flag "UseGdiEmfRenderer" su "false", Aspose.Words utilizzerà il proprio renderer di metafile.
            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Emf);
            saveOptions.UseGdiEmfRenderer = useGdiEmfRenderer;

            doc.Save(ArtifactsDir + "ImageSaveOptions.Renderer.emf", saveOptions);

            // Il renderer GDI+ di solito crea file più grandi.
            if (useGdiEmfRenderer)
#if NET48 || JAVA
                Assert.That(300000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#elif NET5_0_OR_GREATER
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#endif
            else
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
```

### Guarda anche

* class [ImageSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../imagesaveoptions/)
* assemblea [Aspose.Words](../../../)


