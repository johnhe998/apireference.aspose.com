---
title: Watermark.SetImage
second_title: Aspose.Words per .NET API Reference
description: Watermark metodo. Aggiunge la filigrana dellimmagine al documento.
type: docs
weight: 30
url: /it/net/aspose.words/watermark/setimage/
---
## SetImage(Image) {#setimage}

Aggiunge la filigrana dell'immagine al documento.

```csharp
public void SetImage(Image image)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| image | Image | Immagine visualizzata come filigrana. |

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentNullException | Genera quando l'immagine è nulla. |

### Guarda anche

* class [Watermark](../)
* spazio dei nomi [Aspose.Words](../../watermark/)
* assemblea [Aspose.Words](../../../)

---

## SetImage(Image, ImageWatermarkOptions) {#setimage_1}

Aggiunge la filigrana dell'immagine al documento.

```csharp
public void SetImage(Image image, ImageWatermarkOptions options)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| image | Image | Immagine visualizzata come filigrana. |
| options | ImageWatermarkOptions | Definisce opzioni aggiuntive per la filigrana dell'immagine. |

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentNullException | Genera quando l'immagine è nulla. |

### Osservazioni

Se[`ImageWatermarkOptions`](../../imagewatermarkoptions/) è nullo, la filigrana verrà impostata con le opzioni predefinite.

### Esempi

Mostra come creare una filigrana da un'immagine nel file system locale.

```csharp
Document doc = new Document();

            // Modifica l'aspetto della filigrana dell'immagine con un oggetto ImageWatermarkOptions,
            // quindi passalo durante la creazione di una filigrana da un file immagine.
            ImageWatermarkOptions imageWatermarkOptions = new ImageWatermarkOptions();
            imageWatermarkOptions.Scale = 5;
            imageWatermarkOptions.IsWashout = false;

#if NET48 || JAVA
            doc.Watermark.SetImage(Image.FromFile(ImageDir + "Logo.jpg"), imageWatermarkOptions);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
            {
                doc.Watermark.SetImage(image, imageWatermarkOptions);
            }
#endif

            doc.Save(ArtifactsDir + "Document.ImageWatermark.docx");
```

### Guarda anche

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* spazio dei nomi [Aspose.Words](../../watermark/)
* assemblea [Aspose.Words](../../../)

---

## SetImage(string, ImageWatermarkOptions) {#setimage_2}

Aggiunge la filigrana dell'immagine al documento.

```csharp
public void SetImage(string imagePath, ImageWatermarkOptions options)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| imagePath | String | Percorso del file immagine visualizzato come filigrana. |
| options | ImageWatermarkOptions | Definisce opzioni aggiuntive per la filigrana dell'immagine. |

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentNullException | Genera quando il percorso è nullo. |

### Osservazioni

Se[`ImageWatermarkOptions`](../../imagewatermarkoptions/) è nullo, la filigrana verrà impostata con le opzioni predefinite.

### Guarda anche

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* spazio dei nomi [Aspose.Words](../../watermark/)
* assemblea [Aspose.Words](../../../)


