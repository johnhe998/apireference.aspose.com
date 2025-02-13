---
title: ViewOptions.FormsDesign
second_title: Référence de l'API Aspose.Words pour .NET
description: ViewOptions propriété. Spécifie si le document est en mode création de formulaires.
type: docs
weight: 30
url: /fr/net/aspose.words.settings/viewoptions/formsdesign/
---
## ViewOptions.FormsDesign property

Spécifie si le document est en mode création de formulaires.

```csharp
public bool FormsDesign { get; set; }
```

### Remarques

Ne fonctionne actuellement que pour les documents au format WordML.

### Exemples

Montre comment activer/désactiver le mode de conception de formulaires.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Définissez la propriété "FormsDesign" sur "false" pour que le mode de conception des formulaires reste désactivé.
// Définissez la propriété "FormsDesign" sur "true" pour activer le mode de conception des formulaires.
doc.ViewOptions.FormsDesign = useFormsDesign;

doc.Save(ArtifactsDir + "ViewOptions.FormsDesign.xml");

Assert.AreEqual(useFormsDesign,
    File.ReadAllText(ArtifactsDir + "ViewOptions.FormsDesign.xml").Contains("<w:formsDesign />"));
```

### Voir également

* class [ViewOptions](../)
* espace de noms [Aspose.Words.Settings](../../viewoptions/)
* Assemblée [Aspose.Words](../../../)


