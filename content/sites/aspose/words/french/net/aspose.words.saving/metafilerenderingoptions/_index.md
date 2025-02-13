---
title: Class MetafileRenderingOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.MetafileRenderingOptions classe. Permet de spécifier des options de rendu de métafichier supplémentaires.
type: docs
weight: 5020
url: /fr/net/aspose.words.saving/metafilerenderingoptions/
---
## MetafileRenderingOptions class

Permet de spécifier des options de rendu de métafichier supplémentaires.

```csharp
public class MetafileRenderingOptions
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [MetafileRenderingOptions](metafilerenderingoptions/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [EmfPlusDualRenderingMode](../../aspose.words.saving/metafilerenderingoptions/emfplusdualrenderingmode/) { get; set; } | Obtient ou définit une valeur déterminant comment les métafichiers EMF+ Dual doivent être rendus. |
| [EmulateRasterOperations](../../aspose.words.saving/metafilerenderingoptions/emulaterasteroperations/) { get; set; } | Obtient ou définit une valeur déterminant si les opérations raster doivent être émulées ou non. |
| [RenderingMode](../../aspose.words.saving/metafilerenderingoptions/renderingmode/) { get; set; } | Obtient ou définit une valeur déterminant le rendu des images de métafichier. |
| [ScaleWmfFontsToMetafileSize](../../aspose.words.saving/metafilerenderingoptions/scalewmffontstometafilesize/) { get; set; } | Obtient ou définit une valeur déterminant s'il faut ou non mettre à l'échelle les polices dans le métafichier WMF en fonction de la taille du métafichier sur la page. |
| [UseEmfEmbeddedToWmf](../../aspose.words.saving/metafilerenderingoptions/useemfembeddedtowmf/) { get; set; } | Obtient ou définit une valeur déterminant comment les métafichiers WMF avec des métafichiers EMF intégrés doivent être rendus. |

### Exemples

Affiche l'ajout d'un retour au rendu bitmap et la modification du type d'avertissements concernant les enregistrements de métafichiers non pris en charge.

```csharp
{
    Document doc = new Document(MyDir + "WMF with image.docx");

    MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();

    // Définissez la propriété "EmulateRasterOperations" sur "false" pour revenir au bitmap lorsque
    // il rencontre un métafichier, qui nécessitera des opérations raster pour s'afficher dans le PDF de sortie.
    metafileRenderingOptions.EmulateRasterOperations = false;

    // Définissez la propriété "RenderingMode" sur "VectorWithFallback" pour essayer de restituer chaque métafichier à l'aide de graphiques vectoriels.
    metafileRenderingOptions.RenderingMode = MetafileRenderingMode.VectorWithFallback;

    // Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
    // pour modifier la façon dont cette méthode convertit le document en .PDF et applique la configuration
    // dans notre objet MetafileRenderingOptions à l'opération d'enregistrement.
    PdfSaveOptions saveOptions = new PdfSaveOptions();
    saveOptions.MetafileRenderingOptions = metafileRenderingOptions;

    HandleDocumentWarnings callback = new HandleDocumentWarnings();
    doc.WarningCallback = callback;

    doc.Save(ArtifactsDir + "PdfSaveOptions.HandleBinaryRasterWarnings.pdf", saveOptions);

    Assert.AreEqual(1, callback.Warnings.Count);
    Assert.AreEqual("'R2_XORPEN' binary raster operation is partly supported.",
        callback.Warnings[0].Description);
}

/// <summary>
/// Imprime et collecte les avertissements liés à la perte de mise en forme qui se produisent lors de l'enregistrement d'un document.
/// </summary>
public class HandleDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.MinorFormattingLoss)
        {
            Console.WriteLine("Unsupported operation: " + info.Description);
            Warnings.Warning(info);
        }
    }

    public WarningInfoCollection Warnings = new WarningInfoCollection();
}
```

### Voir également

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


