---
title: Modifier les taquets de tabulation de la table des matières dans le document Word
linktitle: Modifier les taquets de tabulation de la table des matières dans le document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à modifier les onglets de la table des matières dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et manipuler des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words, il y a la possibilité de modifier les onglets utilisés dans une table des matières d'un document Word. Dans ce guide, nous allons vous montrer comment utiliser le code source C# de Aspose.Words pour .NET pour modifier les onglets dans la table des matières d'un document.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le traitement de mots avec des documents Word simple et efficace. Il offre un large éventail de fonctionnalités pour créer, éditer et manipuler des documents Word, y compris la modification des onglets de la table des matières.

## Chargement du document contenant la table des matières

La première étape consiste à charger le document Word contenant la table des matières que vous souhaitez modifier. Utilisez la classe Document pour charger le document à partir du fichier source. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Dans cet exemple, nous chargeons le document "Table of contents.docx" situé dans le répertoire documents.

## Changement d'onglet dans la table des matières

Une fois le document chargé, nous parcourons chaque paragraphe du document et vérifions s'il est formaté à l'aide des styles de résultat de la table des matières (TOC). Si c'est le cas, nous modifions les onglets utilisés pour aligner les numéros de page. Voici comment:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

Dans cet exemple, nous utilisons une boucle pour parcourir chaque paragraphe du document. Nous vérifions ensuite si le paragraphe est formaté à l'aide des styles Table of Contents Result (TOC). Si tel est le cas, nous accédons au premier onglet utilisé dans ce paragraphe et le modifions en supprimant l'ancien onglet et en ajoutant un nouvel onglet avec une position modifiée.

## Enregistrer le document modifié

Une fois que vous avez apporté les modifications nécessaires aux onglets de la table des matières, vous pouvez enregistrer le document modifié à l'aide de la méthode Save de la classe Document. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Dans cet exemple, nous enregistrons le document modifié sous "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Exemple de code source pour la fonctionnalité "Modifier les onglets de la table des matières" avec Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document contenant la table des matières
Document doc = new Document(dataDir + "Table of contents.docx");

// Modifier les onglets de la table des matières
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour modifier les onglets dans la table des matières d'un document Word à l'aide du code source C# fourni. En suivant les étapes fournies, vous pouvez facilement personnaliser les onglets de la table des matières de vos documents Word dans votre application C#. Aspose.Words offre une flexibilité et une puissance considérables pour travailler avec les styles et la mise en forme de vos documents, vous permettant de créer des documents Word attrayants et professionnels.

### FAQ sur les tabulations de changement de toc dans un document Word

#### Q : Quel est l'objectif de la fonctionnalité "Change Toc Tab Stops In Word Document" dans Aspose.Words pour .NET ?

R : La fonctionnalité "Change Toc Tab Stops In Word Document" dans Aspose.Words pour .NET vous permet de modifier les taquets de tabulation utilisés dans la table des matières d'un document Word. Il vous permet de personnaliser l'alignement et le positionnement des numéros de page et des titres correspondants dans la table des matières.

#### Q : Qu'est-ce qu'Aspose.Words pour .NET ?

R : Aspose.Words pour .NET est une bibliothèque puissante conçue pour le traitement de mots avec des documents Word dans des applications .NET. Il fournit des fonctionnalités complètes pour créer, modifier, manipuler et convertir des documents Word par programmation à l'aide de C # ou d'autres langages .NET.

#### Q : Comment charger un document Word contenant une table des matières à l'aide d'Aspose.Words pour .NET ?

 R : Pour charger un document Word contenant une table des matières à l'aide d'Aspose.Words pour .NET, vous pouvez utiliser le`Document` classe et son constructeur. En fournissant le chemin d'accès au fichier du document, vous pouvez le charger dans un`Document` objet. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Cet extrait de code charge le document "Table of contents.docx" situé dans le répertoire spécifié.

#### Q : Comment puis-je modifier les onglets utilisés dans la table des matières à l'aide d'Aspose.Words pour .NET ?

 R : Une fois le document chargé, vous pouvez parcourir chaque paragraphe du document et vérifier s'il est formaté à l'aide des styles de résultat de la table des matières (TOC). Si un paragraphe est formaté en tant que style TOC, vous pouvez modifier les tabulations utilisées pour aligner les numéros de page. Dans Aspose.Words pour .NET, vous pouvez accéder au`ParagraphFormat` propriété de chaque paragraphe pour récupérer et modifier les taquets de tabulation. Voici un exemple :

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

Dans ce code, la boucle parcourt chaque paragraphe du document. Si un paragraphe a un style TOC, il accède au premier taquet de tabulation utilisé dans ce paragraphe, le supprime et ajoute un nouveau taquet de tabulation avec une position modifiée.

#### Q : Puis-je modifier les onglets pour plusieurs niveaux dans la table des matières à l'aide d'Aspose.Words pour .NET ?

R : Oui, vous pouvez modifier les onglets pour plusieurs niveaux dans la table des matières à l'aide d'Aspose.Words pour .NET. En parcourant chaque paragraphe et en vérifiant le style TOC, vous pouvez modifier les onglets pour chaque niveau individuellement. Vous pouvez accéder au niveau souhaité de la table des matières et ajuster les taquets de tabulation en conséquence.

#### Q : Comment enregistrer le document modifié après avoir modifié les onglets dans la table des matières à l'aide d'Aspose.Words pour .NET ?

 R : Après avoir apporté les modifications nécessaires aux onglets de la table des matières, vous pouvez enregistrer le document modifié à l'aide de la`Save` méthode de la`Document` classe. Indiquez le chemin d'accès au fichier et le nom souhaités pour le document de sortie en tant que paramètre du`Save` méthode. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Ce code enregistre le document modifié sous "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### Q : Puis-je personnaliser d'autres aspects de la table des matières à l'aide d'Aspose.Words pour .NET ?

R : Oui, avec Aspose.Words pour .NET, vous pouvez personnaliser divers aspects de la table des matières. Outre la modification des onglets, vous pouvez modifier les styles de police, la taille, l'alignement et d'autres propriétés de mise en forme des entrées de la table des matières et des numéros de page. De plus, vous pouvez ajuster l'indentation, l'espacement et la mise en forme des titres correspondants.

#### Q :. Puis-je modifier l'alignement des tabulations et les caractères de début de la table des matières à l'aide d'Aspose.Words pour .NET ?

R : Oui, vous pouvez modifier l'alignement des tabulations et les caractères de début de la table des matières à l'aide d'Aspose.Words pour .NET. En accédant aux taquets de tabulation et en ajustant leurs propriétés d'alignement et de ligne de repère, vous pouvez contrôler l'alignement et l'apparence visuelle des numéros de page et des titres correspondants dans la table des matières.

#### Q : Aspose.Words pour .NET prend-il en charge la modification d'autres styles et formatages dans les documents Word ?

: Oui, Aspose.Words pour .NET fournit une prise en charge étendue pour modifier divers styles et formatages dans les documents Word. Il vous permet de modifier les styles de différents éléments tels que les paragraphes, les titres, les tableaux, les listes, etc. Vous pouvez modifier les polices, les couleurs, l'alignement, l'indentation, l'espacement et d'autres aspects de mise en forme en fonction de vos besoins.

#### Q : Puis-je modifier les onglets de la table des matières dans un document Word existant à l'aide d'Aspose.Words pour .NET ?

R : Oui, vous pouvez modifier les onglets de la table des matières dans un document Word existant à l'aide d'Aspose.Words pour .NET. En chargeant le document, en parcourant les paragraphes et en apportant les modifications nécessaires aux taquets de tabulation, vous pouvez mettre à jour les onglets dans la table des matières. Enfin, enregistrez le document pour appliquer les modifications.