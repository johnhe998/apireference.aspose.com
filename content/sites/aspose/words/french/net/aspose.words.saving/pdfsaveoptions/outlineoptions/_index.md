---
title: PdfSaveOptions.OutlineOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfSaveOptions propriété. Permet de spécifier les options de contour.
type: docs
weight: 210
url: /fr/net/aspose.words.saving/pdfsaveoptions/outlineoptions/
---
## PdfSaveOptions.OutlineOptions property

Permet de spécifier les options de contour.

```csharp
public OutlineOptions OutlineOptions { get; }
```

### Remarques

Les contours peuvent être créés à partir d'en-têtes et de signets.

Pour les titres, le niveau hiérarchique est déterminé par le niveau du titre.

Il est possible de définir le niveau de titre maximum à inclure dans les contours ou de désactiver complètement les contours de titre.

Pour les signets, le niveau hiérarchique peut être défini dans les options comme valeur par défaut pour tous les signets ou comme valeurs individuelles pour des signets particuliers.

De plus, les contours peuvent être exportés au format XPS en utilisant le même`OutlineOptions` classer.

### Exemples

Montre comment limiter le niveau des titres qui apparaîtront dans le plan d'un document PDF enregistré.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérer des en-têtes pouvant servir d'entrées de table des matières des niveaux 1, 2, puis 3.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.SaveFormat = SaveFormat.Pdf;

// Le document PDF de sortie contiendra un plan, qui est une table des matières qui répertorie les en-têtes dans le corps du document.
// Cliquer sur une entrée dans ce plan nous amènera à l'emplacement de son en-tête respectif.
// Définissez la propriété "HeadingsOutlineLevels" sur "2" pour exclure tous les titres dont les niveaux sont supérieurs à 2 du plan.
// Les deux derniers titres que nous avons insérés ci-dessus n'apparaîtront pas.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 2;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeadingsOutlineLevels.pdf", saveOptions);
```

Montre comment travailler avec des niveaux hiérarchiques qui ne contiennent aucun en-tête correspondant lors de l'enregistrement d'un document PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérer des en-têtes pouvant servir d'entrées de table des matières des niveaux 1 et 5.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.1.1.1.1");
builder.Writeln("Heading 1.1.1.1.2");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Le document PDF de sortie contiendra un plan, qui est une table des matières qui répertorie les en-têtes dans le corps du document.
// Cliquer sur une entrée dans ce plan nous amènera à l'emplacement de son en-tête respectif.
// Définissez la propriété "HeadingsOutlineLevels" sur "5" pour inclure tous les titres de niveaux 5 et inférieurs dans le plan.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 5;

 // Ce document contient des titres de niveaux 1 et 5, et aucun titre de niveaux 2, 3 et 4.
// Le document PDF de sortie traitera les niveaux hiérarchiques 2, 3 et 4 comme "manquants".
// Définissez la propriété "CreateMissingOutlineLevels" sur "true" pour inclure tous les niveaux manquants dans le plan,
// laissant des entrées de contour vides car il n'y a pas d'en-têtes utilisables.
// Définissez la propriété "CreateMissingOutlineLevels" sur "false" pour ignorer les niveaux hiérarchiques manquants,
// et traiter les en-têtes de niveau hiérarchique 5 comme niveau 2.
saveOptions.OutlineOptions.CreateMissingOutlineLevels = createMissingOutlineLevels;

doc.Save(ArtifactsDir + "PdfSaveOptions.CreateMissingOutlineLevels.pdf", saveOptions);
```

### Voir également

* class [OutlineOptions](../../outlineoptions/)
* class [PdfSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pdfsaveoptions/)
* Assemblée [Aspose.Words](../../../)


