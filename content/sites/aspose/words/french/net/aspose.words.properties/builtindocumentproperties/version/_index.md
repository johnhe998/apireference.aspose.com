---
title: BuiltInDocumentProperties.Version
second_title: Référence de l'API Aspose.Words pour .NET
description: BuiltInDocumentProperties propriété. Représente le numéro de version de lapplication qui a créé le document.
type: docs
weight: 320
url: /fr/net/aspose.words.properties/builtindocumentproperties/version/
---
## BuiltInDocumentProperties.Version property

Représente le numéro de version de l'application qui a créé le document.

```csharp
public int Version { get; set; }
```

### Remarques

Lorsqu'un document a été créé par Microsoft Word, les 16 bits supérieurs représentent la version principale et les 16 bits inférieurs représentent le numéro de build.

### Exemples

Montre comment travailler avec les propriétés du document dans la catégorie "Origine".

```csharp
// Ouvre un document que nous avons créé et modifié à l'aide de Microsoft Word.
Document doc = new Document(MyDir + "Properties.docx");
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// Les propriétés intégrées suivantes contiennent des informations concernant la création et la modification de ce document.
// Nous pouvons cliquer avec le bouton droit sur ce document dans l'Explorateur Windows et trouver
// ces propriétés via "Propriétés" -> "Détails" -> Catégorie "Origine".
// Des champs tels que PRINTDATE et EDITTIME peuvent afficher ces valeurs dans le corps du document.
Console.WriteLine($"Created using {properties.NameOfApplication}, on {properties.CreatedTime}");
Console.WriteLine($"Minutes spent editing: {properties.TotalEditingTime}");
Console.WriteLine($"Date/time last printed: {properties.LastPrinted}");
Console.WriteLine($"Template document: {properties.Template}");

// Nous pouvons également modifier les valeurs des propriétés intégrées.
properties.Company = "Doe Ltd.";
properties.Manager = "Jane Doe";
properties.Version = 5;
properties.RevisionNumber++;

// Microsoft Word met automatiquement à jour les propriétés suivantes lorsque nous enregistrons le document.
// Pour utiliser ces propriétés avec Aspose.Words, nous devrons leur définir des valeurs manuellement.
properties.LastSavedBy = "John Doe";
properties.LastSavedTime = DateTime.Now;

// Nous pouvons cliquer avec le bouton droit sur ce document dans l'Explorateur Windows et trouver these properties in "Properties" -> "Details" -> "Origin".
doc.Save(ArtifactsDir + "DocumentProperties.Origin.docx");
```

### Voir également

* class [BuiltInDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../builtindocumentproperties/)
* Assemblée [Aspose.Words](../../../)


