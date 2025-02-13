---
title: HtmlLoadOptions.SupportVml
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlLoadOptions propriété. Obtient ou définit une valeur indiquant sil faut prendre en charge les images VML.
type: docs
weight: 60
url: /fr/net/aspose.words.loading/htmlloadoptions/supportvml/
---
## HtmlLoadOptions.SupportVml property

Obtient ou définit une valeur indiquant s'il faut prendre en charge les images VML.

```csharp
public bool SupportVml { get; set; }
```

### Exemples

Montre comment prendre en charge les commentaires conditionnels lors du chargement d'un document HTML.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// Si la valeur est true, alors nous prenons en compte le code VML lors de l'analyse du document chargé.
loadOptions.SupportVml = supportVml;

// Ce document contient une image JPEG dans "<!--[if gte vml 1]>" Mots clés,
// et une image PNG différente dans "<![if !vml]>" Mots clés.
// Si nous définissons le drapeau "SupportVml" sur "true", alors Aspose.Words chargera le JPEG.
// Si nous définissons cet indicateur sur "false", alors Aspose.Words ne chargera que le PNG.
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### Voir également

* class [HtmlLoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../htmlloadoptions/)
* Assemblée [Aspose.Words](../../../)


