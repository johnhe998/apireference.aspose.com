---
title: BuiltInDocumentProperties.LastPrinted
second_title: Référence de l'API Aspose.Words pour .NET
description: BuiltInDocumentProperties propriété. Obtient ou définit la date à laquelle le document a été imprimé pour la dernière fois en UTC.
type: docs
weight: 150
url: /fr/net/aspose.words.properties/builtindocumentproperties/lastprinted/
---
## BuiltInDocumentProperties.LastPrinted property

Obtient ou définit la date à laquelle le document a été imprimé pour la dernière fois en UTC.

```csharp
public DateTime LastPrinted { get; set; }
```

### Remarques

Pour les documents provenant du format RTF, cette propriété renvoie l'heure locale de la dernière opération d'impression.

Si le document n'a jamais été imprimé, cette propriété renverra DateTime.MinValue.

Aspose.Words ne met pas à jour cette propriété.

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


