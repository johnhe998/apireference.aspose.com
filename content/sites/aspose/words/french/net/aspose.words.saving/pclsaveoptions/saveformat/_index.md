---
title: PclSaveOptions.SaveFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: PclSaveOptions propriété. Spécifie le format dans lequel le document sera enregistré si cet objet doptions denregistrement est utilisé. Ne peut êtrePcl .
type: docs
weight: 40
url: /fr/net/aspose.words.saving/pclsaveoptions/saveformat/
---
## PclSaveOptions.SaveFormat property

Spécifie le format dans lequel le document sera enregistré si cet objet d'options d'enregistrement est utilisé. Ne peut êtrePcl .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Exemples

Montre comment pixelliser des éléments complexes lors de l'enregistrement d'un document au format PCL.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### Voir également

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [PclSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pclsaveoptions/)
* Assemblée [Aspose.Words](../../../)


