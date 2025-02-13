---
title: SvgSaveOptions.FitToViewPort
second_title: Référence de l'API Aspose.Words pour .NET
description: SvgSaveOptions propriété. Spécifie si le SVG de sortie doit remplir la zone de la fenêtre daffichage disponible fenêtre du navigateur ou conteneur. Lorsquil est défini sur la largeur et la hauteur réelles du SVG de sortie il est défini sur 100 .
type: docs
weight: 30
url: /fr/net/aspose.words.saving/svgsaveoptions/fittoviewport/
---
## SvgSaveOptions.FitToViewPort property

Spécifie si le SVG de sortie doit remplir la zone de la fenêtre d'affichage disponible (fenêtre du navigateur ou conteneur). Lorsqu'il est défini sur la largeur et la hauteur réelles du SVG de sortie, il est défini sur 100 %.

La valeur par défaut est faux.

```csharp
public bool FitToViewPort { get; set; }
```

### Exemples

Montre comment imiter les propriétés des images lors de la conversion d'un document .docx en .svg.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Configurez l'objet SvgSaveOptions pour enregistrer sans bordures de page ni texte sélectionnable.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### Voir également

* class [SvgSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../svgsaveoptions/)
* Assemblée [Aspose.Words](../../../)


