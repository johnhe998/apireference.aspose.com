---
title: RtfSaveOptions.SaveImagesAsWmf
second_title: Aspose.Words per .NET API Reference
description: RtfSaveOptions proprietà. Quando true tutte le immagini verranno salvate come WMF.
type: docs
weight: 50
url: /it/net/aspose.words.saving/rtfsaveoptions/saveimagesaswmf/
---
## RtfSaveOptions.SaveImagesAsWmf property

Quando true tutte le immagini verranno salvate come WMF.

```csharp
public bool SaveImagesAsWmf { get; set; }
```

### Osservazioni

Questa opzione potrebbe aiutare a evitare i messaggi di avviso di WordPad.

### Esempi

Mostra come convertire tutte le immagini in un documento nel formato Windows Metafile mentre salviamo il documento come RTF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
Shape imageShape = builder.InsertImage(ImageDir + "Logo.jpg");

Assert.AreEqual(ImageType.Jpeg, imageShape.ImageData.ImageType);

builder.InsertParagraph();
builder.Writeln("Png image:");
imageShape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ImageType.Png, imageShape.ImageData.ImageType);

// Crea un oggetto "RtfSaveOptions" da passare al metodo "Salva" del documento per modificare il modo in cui lo salviamo in un RTF.
RtfSaveOptions rtfSaveOptions = new RtfSaveOptions();

// Imposta la proprietà "SaveImagesAsWmf" su "true" per convertire tutte le immagini nel documento in WMF mentre lo salviamo in RTF.
// In questo modo aiuterai lettori come WordPad a leggere il nostro documento.
// Imposta la proprietà "SaveImagesAsWmf" su "false" per preservare il formato originale di tutte le immagini nel documento
// mentre lo salviamo in RTF. Ciò manterrà la qualità delle immagini a scapito della compatibilità con i lettori RTF più vecchi.
rtfSaveOptions.SaveImagesAsWmf = saveImagesAsWmf;

doc.Save(ArtifactsDir + "RtfSaveOptions.SaveImagesAsWmf.rtf", rtfSaveOptions);

doc = new Document(ArtifactsDir + "RtfSaveOptions.SaveImagesAsWmf.rtf");

NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

if (saveImagesAsWmf)
{
    Assert.AreEqual(ImageType.Wmf, ((Shape)shapes[0]).ImageData.ImageType);
    Assert.AreEqual(ImageType.Wmf, ((Shape)shapes[1]).ImageData.ImageType);
}
else
{
    Assert.AreEqual(ImageType.Jpeg, ((Shape)shapes[0]).ImageData.ImageType);
    Assert.AreEqual(ImageType.Png, ((Shape)shapes[1]).ImageData.ImageType);
}
```

### Guarda anche

* class [RtfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../rtfsaveoptions/)
* assemblea [Aspose.Words](../../../)


