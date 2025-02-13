---
title: Enum ImlRenderingMode
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.ImlRenderingMode énumération. Spécifie comment les objets dencre InkML sont rendus aux formats de page fixes.
type: docs
weight: 4990
url: /fr/net/aspose.words.saving/imlrenderingmode/
---
## ImlRenderingMode enumeration

Spécifie comment les objets d'encre (InkML) sont rendus aux formats de page fixes.

```csharp
public enum ImlRenderingMode
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Fallback | `0` | Si la forme de repli est disponible pour l'objet d'encre (InkML), Aspose.Words rend la forme de repli au lieu de InkML. |
| InkML | `1` | Aspose.Words ignore la forme de repli de l'objet d'encre (InkML) et rend InkML lui-même. Il s'agit du mode par défaut. |

### Exemples

Montre comment rendre l'objet Ink.

```csharp
Document doc = new Document(MyDir + "Ink object.docx");

// Set 'ImlRenderingMode.InkML' ignore la forme de repli de l'objet d'encre (InkML) et rend InkML lui-même.
// Si le résultat du rendu n'est pas satisfaisant,
// veuillez utiliser 'ImlRenderingMode.Fallback' pour obtenir un résultat similaire aux versions précédentes.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg)
{
    ImlRenderingMode = ImlRenderingMode.InkML
};

doc.Save(ArtifactsDir + "ImageSaveOptions.RenderInkObject.jpeg", saveOptions);
```

### Voir également

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


