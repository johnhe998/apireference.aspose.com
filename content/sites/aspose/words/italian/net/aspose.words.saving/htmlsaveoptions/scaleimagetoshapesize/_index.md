---
title: HtmlSaveOptions.ScaleImageToShapeSize
second_title: Aspose.Words per .NET API Reference
description: HtmlSaveOptions proprietà. Specifica se le immagini vengono ridimensionate da Aspose.Words alla dimensione della forma di delimitazione durante lesportazione in HTML MHTML o EPUB. Il valore predefinito èVERO .
type: docs
weight: 450
url: /it/net/aspose.words.saving/htmlsaveoptions/scaleimagetoshapesize/
---
## HtmlSaveOptions.ScaleImageToShapeSize property

Specifica se le immagini vengono ridimensionate da Aspose.Words alla dimensione della forma di delimitazione durante l'esportazione in HTML, MHTML o EPUB. Il valore predefinito è`VERO` .

```csharp
public bool ScaleImageToShapeSize { get; set; }
```

### Osservazioni

Un'immagine in un documento di Microsoft Word è una forma. La forma ha una dimensione e l'immagine ha la sua dimensione. Le taglie non sono direttamente collegate. Ad esempio, l'immagine può essere 1024x786 pixel, ma la forma che visualizza questa immagine può essere 400x300 punti.

Per visualizzare un'immagine nel browser, deve essere ridimensionata alla dimensione della forma. Il`ScaleImageToShapeSize` la proprietà controlla dove avviene il ridimensionamento dell'immagine : in Aspose.Words durante l'esportazione in HTML o nel browser durante la visualizzazione del documento.

quando`ScaleImageToShapeSize` è`VERO` , l'immagine viene ridimensionata da Aspose.Words utilizzando un ridimensionamento di alta qualità durante l'esportazione in HTML. quando`ScaleImageToShapeSize` è`falso`l'immagine viene emessa con le sue dimensioni originali e il browser deve ridimensionarla.

In generale, i browser eseguono un ridimensionamento rapido e di scarsa qualità. Di conseguenza, normalmente otterrai una migliore qualità di visualizzazione nel browser e dimensioni del file inferiori quando`ScaleImageToShapeSize` è`VERO` , ma una migliore qualità di stampa e una conversione più rapida quando`ScaleImageToShapeSize` è`falso`.

### Esempi

Mostra come disabilitare il ridimensionamento delle immagini alle dimensioni della loro forma padre durante il salvataggio in .html.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            // Inserisci una forma che contenga un'immagine, quindi rendi quella forma notevolmente più piccola dell'immagine.
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            Shape imageShape = builder.InsertImage(image);
            imageShape.Width = 50;
            imageShape.Height = 50;

            // Il salvataggio di un documento che contiene forme con immagini in HTML creerà un file immagine nel file system locale
            // per ciascuna di queste forme. Il documento HTML di output utilizzerà <image> tag per collegare e visualizzare queste immagini.
            // Quando salviamo il documento in HTML, possiamo passare un oggetto SaveOptions per determinare
            // se ridimensionare tutte le immagini che si trovano all'interno delle forme alle dimensioni delle loro forme.
            // L'impostazione del flag "ScaleImageToShapeSize" su "true" ridurrà ogni immagine
            // alla dimensione della forma che la contiene, in modo che nessuna immagine salvata sia più grande di quanto il documento richiede che siano.
            // L'impostazione del flag "ScaleImageToShapeSize" su "false" conserverà le dimensioni originali di queste immagini,
            // che occuperà più spazio in cambio della conservazione della qualità dell'immagine.
            HtmlSaveOptions options = new HtmlSaveOptions { ScaleImageToShapeSize = scaleImageToShapeSize };

            doc.Save(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.html", options);

            FileInfo fileInfo = new FileInfo(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.001.png");

#if NET48 || JAVA
        if (scaleImageToShapeSize)
            Assert.That(3000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(20000, Is.LessThan(fileInfo.Length));
#elif NET5_0_OR_GREATER
        if (scaleImageToShapeSize)
            Assert.That(10000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(30000, Is.LessThan(fileInfo.Length));
#endif
```

### Guarda anche

* property [ImageResolution](../imageresolution/)
* class [HtmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


