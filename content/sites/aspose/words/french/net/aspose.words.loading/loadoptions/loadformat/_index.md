---
title: LoadOptions.LoadFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: LoadOptions propriété. Spécifie le format du document à charger. La valeur par défaut estAuto .
type: docs
weight: 90
url: /fr/net/aspose.words.loading/loadoptions/loadformat/
---
## LoadOptions.LoadFormat property

Spécifie le format du document à charger. La valeur par défaut estAuto .

```csharp
public LoadFormat LoadFormat { get; set; }
```

### Remarques

Il est recommandé de spécifier leAutovalue et laissez Aspose.Words detect le format de fichier automatiquement. Si vous connaissez le format du document que vous êtes sur le point de charger, vous pouvez spécifier explicitement le format et cela réduira légèrement le temps de chargement par la surcharge associée à la détection automatique du format. Si vous spécifiez un format de chargement explicite et qu'il deviendra s'avère erroné, la détection automatique sera invoquée et une seconde tentative de chargement du fichier sera effectuée.

### Exemples

Montre comment spécifier un URI de base lors de l'ouverture d'un document html.

```csharp
// Supposons que nous voulions charger un document .html contenant une image liée par une URI relative
// alors que l'image est dans un endroit différent. Dans ce cas, nous devrons résoudre l'URI relatif en un absolu.
 // Nous pouvons fournir un URI de base en utilisant un objet HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// Alors que l'image était cassée dans l'entrée .html, notre URI de base personnalisé nous a aidés à réparer le lien.
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// Ce document de sortie affichera l'image manquante.
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

### Voir également

* enum [LoadFormat](../../../aspose.words/loadformat/)
* class [LoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../loadoptions/)
* Assemblée [Aspose.Words](../../../)


