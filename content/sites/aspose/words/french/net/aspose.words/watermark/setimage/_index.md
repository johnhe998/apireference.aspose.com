---
title: Watermark.SetImage
second_title: Référence de l'API Aspose.Words pour .NET
description: Watermark méthode. Ajoute un filigrane dimage dans le document.
type: docs
weight: 30
url: /fr/net/aspose.words/watermark/setimage/
---
## SetImage(Image) {#setimage}

Ajoute un filigrane d'image dans le document.

```csharp
public void SetImage(Image image)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| image | Image | Image affichée en filigrane. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Lance lorsque l'image est nulle. |

### Voir également

* class [Watermark](../)
* espace de noms [Aspose.Words](../../watermark/)
* Assemblée [Aspose.Words](../../../)

---

## SetImage(Image, ImageWatermarkOptions) {#setimage_1}

Ajoute un filigrane d'image dans le document.

```csharp
public void SetImage(Image image, ImageWatermarkOptions options)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| image | Image | Image affichée en filigrane. |
| options | ImageWatermarkOptions | Définit des options supplémentaires pour le filigrane d'image. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Lance lorsque l'image est nulle. |

### Remarques

Si[`ImageWatermarkOptions`](../../imagewatermarkoptions/) est nul, le filigrane sera défini avec les options par défaut.

### Exemples

Montre comment créer un filigrane à partir d'une image dans le système de fichiers local.

```csharp
Document doc = new Document();

            // Modifier l'apparence du filigrane de l'image avec un objet ImageWatermarkOptions,
            // puis passez-le lors de la création d'un filigrane à partir d'un fichier image.
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

### Voir également

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* espace de noms [Aspose.Words](../../watermark/)
* Assemblée [Aspose.Words](../../../)

---

## SetImage(string, ImageWatermarkOptions) {#setimage_2}

Ajoute un filigrane d'image dans le document.

```csharp
public void SetImage(string imagePath, ImageWatermarkOptions options)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| imagePath | String | Chemin d'accès au fichier image affiché en filigrane. |
| options | ImageWatermarkOptions | Définit des options supplémentaires pour le filigrane d'image. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Lance lorsque le chemin est nul. |

### Remarques

Si[`ImageWatermarkOptions`](../../imagewatermarkoptions/) est nul, le filigrane sera défini avec les options par défaut.

### Voir également

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* espace de noms [Aspose.Words](../../watermark/)
* Assemblée [Aspose.Words](../../../)


