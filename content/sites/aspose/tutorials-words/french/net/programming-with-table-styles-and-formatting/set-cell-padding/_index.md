---
title: Définir le rembourrage des cellules
linktitle: Définir le rembourrage des cellules
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir les marges des cellules de tableau à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de définition des marges des cellules de tableau à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment ajuster les marges gauche, supérieure, droite et inférieure (espace) du contenu des cellules dans vos tableaux dans vos documents Word à l'aide de Aspose.Words pour .NET .

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document Word modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Ensuite, vous devez créer une nouvelle instance de`Document` classe et un constructeur de document pour ce document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Commencez un nouveau tableau et ajoutez une cellule
Pour commencer à créer le tableau, nous utilisons le`StartTable()` méthode du constructeur de document, puis nous ajoutons une cellule au tableau en utilisant la`InsertCell()` méthode.

```csharp
builder. StartTable();
builder. InsertCell();
```

## Étape 4 : Définir les marges des cellules
 Nous pouvons maintenant définir les marges des cellules à l'aide de la`SetPaddings()` méthode de la`CellFormat` objet. Les marges sont définies en points et spécifiées dans l'ordre gauche, haut, droite et bas.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Étape 5 : Ajouter du contenu à la cellule
 Ensuite, nous pouvons ajouter du contenu à la cellule en utilisant le générateur de document`Writeln()` méthode.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Étape 6 : Terminez le tableau et enregistrez le document
 Enfin, nous terminons la création du tableau en utilisant le`EndRow()` méthode et`EndTable()`, puis nous enregistrons le document modifié dans un fichier.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Exemple de code source pour Set Cell Padding à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Définit la quantité d'espace (en points) à ajouter à gauche/en haut/à droite/en bas du contenu de la cellule.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir les marges d'une cellule de tableau à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement ajuster les marges des cellules pour créer des espaces à gauche, en haut, à droite et en bas du contenu de vos tableaux dans vos documents Word. Aspose.Words offre une API puissante et flexible pour manipuler et formater des tableaux dans vos documents. Grâce à ces connaissances, vous pouvez personnaliser la mise en forme de vos tableaux en fonction de vos besoins spécifiques.