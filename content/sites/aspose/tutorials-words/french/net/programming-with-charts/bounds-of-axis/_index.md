---
title: Limites de l'axe dans un graphique
linktitle: Limites de l'axe dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à définir les limites d'un axe dans un graphique à l'aide de Aspose.Words pour .NET contrôlant la plage de valeurs affichées sur l'axe.
type: docs
weight: 10
url: /fr/net/programming-with-charts/bounds-of-axis/
---

Ce didacticiel explique comment définir les limites d'un axe dans un graphique à l'aide de Aspose.Words pour .NET. En insérant un graphique, en ajoutant des données de série et en configurant la mise à l'échelle de l'axe, vous pouvez définir les valeurs minimale et maximale de l'axe.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de texte avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet de travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer et configurer un graphique
 Insérez un graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder` objet. Définissez le type et les dimensions de graphique souhaités.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 4 : Ajouter des données de série
Effacez toutes les séries existantes dans le graphique et ajoutez de nouvelles données de série. Dans cet exemple, nous ajoutons une série avec des étiquettes "Item 1" à "Item 5" et les valeurs correspondantes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Étape 5 : définir les limites de l'axe
 Configurez la mise à l'échelle de l'axe Y en définissant les valeurs minimale et maximale à l'aide des`Scaling.Minimum` et`Scaling.Maximum` propriétés de l'axe.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Étape 6 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Exemple de code source pour Bounds Of Axis utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

C'est ça! Vous avez défini avec succès les limites d'un axe dans un graphique à l'aide de Aspose.Words pour .NET.

## Conclusion
Dans ce didacticiel, vous avez appris à définir les limites d'un axe dans un graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape, vous pouvez insérer et configurer un graphique, ajouter des données de série et définir les valeurs minimale et maximale pour la mise à l'échelle de l'axe. Aspose.Words pour .NET fournit une API puissante et flexible pour le traitement de mots avec des documents Word, vous permettant de créer facilement des graphiques dynamiques et visuellement attrayants.


### FAQ

#### Q1. Qu'est-ce qu'Aspose.Words pour .NET ?
Aspose.Words pour .NET est une bibliothèque qui permet aux développeurs de travailler avec des documents Word par programmation. Il fournit un large éventail de fonctionnalités et de fonctionnalités pour créer, manipuler et enregistrer des documents Word.

#### Q2. Comment puis-je installer Aspose.Words pour .NET ?
Pour installer Aspose.Words pour .NET, vous pouvez utiliser le gestionnaire de packages NuGet dans Visual Studio. Recherchez simplement "Aspose.Words" dans le gestionnaire de packages NuGet et installez-le dans votre projet.

#### Q3. Puis-je utiliser Aspose.Words pour .NET avec d'autres langages de programmation ?
Non, Aspose.Words pour .NET est spécialement conçu pour les applications .NET. Il fonctionne avec des langages de programmation tels que C# et VB.NET.

#### Q4. Existe-t-il d'autres prérequis pour utiliser Aspose.Words pour .NET ?
Outre l'installation de la bibliothèque Aspose.Words pour .NET, vous devez avoir une connaissance de base de la programmation C # et du traitement de mots avec des documents Word. Une connaissance du framework .NET sera également utile.
