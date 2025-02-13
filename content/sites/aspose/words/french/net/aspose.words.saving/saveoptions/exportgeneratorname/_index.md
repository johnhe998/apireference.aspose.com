---
title: SaveOptions.ExportGeneratorName
second_title: Référence de l'API Aspose.Words pour .NET
description: SaveOptions propriété. Lorsquil est vrai le nom et la version de Aspose.Words sont intégrés dans les fichiers produits. La valeur par défaut est vrai .
type: docs
weight: 80
url: /fr/net/aspose.words.saving/saveoptions/exportgeneratorname/
---
## SaveOptions.ExportGeneratorName property

Lorsqu'il est vrai, le nom et la version de Aspose.Words sont intégrés dans les fichiers produits. La valeur par défaut est **vrai** .

```csharp
public bool ExportGeneratorName { get; set; }
```

### Exemples

Montre comment désactiver l'ajout du nom et de la version de Aspose.Words dans les fichiers produits.

```csharp
Document doc = new Document();

// Utilisez https://docs.aspose.com/words/net/generator-or-producer-name-included-in-output-documents/ pour savoir comment vérifier le résultat.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { ExportGeneratorName = false };

doc.Save(ArtifactsDir + "OoxmlSaveOptions.ExportGeneratorName.docx", saveOptions);
```

### Voir également

* class [SaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../saveoptions/)
* Assemblée [Aspose.Words](../../../)


