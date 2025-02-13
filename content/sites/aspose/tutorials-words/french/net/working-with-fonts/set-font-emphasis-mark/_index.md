---
title: Définir la marque d'accentuation de la police
linktitle: Définir la marque d'accentuation de la police
second_title: API de traitement de documents Aspose.Words
description: Apprenez à définir le style d'accentuation de la police dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-font-emphasis-mark/
---

Dans ce didacticiel, nous allons vous montrer comment définir le style d'accentuation de la police dans un document Word à l'aide de Aspose.Words pour .NET. L'accentuation de la police est utilisée pour mettre en évidence certains mots ou expressions dans le texte.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
 Commencez par définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créez et personnalisez le document
 Créer une instance de`Document` classe et un associé`DocumentBuilder` pour construire le contenu du document. Utilisez le`Font.EmphasisMark` propriété pour définir le style d'accentuation de la police sur`EmphasisMark.UnderSolidCircle` . Utilisez ensuite le`Write` et`Writeln` méthodes de la`DocumentBuilder` pour ajouter du texte avec l'emphase de police spécifiée.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Étape 3 : Enregistrez le document
 Enregistrez le document à l'aide de la`Save` méthode de la`Document` avec le chemin et le nom de fichier appropriés.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Exemple de code source pour Set Font Emphasis Mark à l'aide de Aspose.Words pour .NET 

```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusion
Dans ce didacticiel, vous avez appris à définir le style d'accentuation de la police dans un document Word à l'aide de Aspose.Words pour .NET. Expérimentez avec différents styles d'emphase et utilisez cette fonctionnalité pour mettre en évidence des mots ou des phrases dans vos documents.

### FAQ

#### Q : Comment puis-je ajouter des accents à une police spécifique dans un document Word à l'aide d'Aspose.Words ?

R : Pour ajouter des accents à une police spécifique dans un document Word à l'aide d'Aspose.Words, vous pouvez utiliser l'API pour accéder à la police souhaitée et appliquer les accents appropriés. Cela ajoutera des accents au texte avec la police sélectionnée.

#### Q : Est-il possible de modifier le style des accents dans un document Word avec Aspose.Words ?

R : Oui, avec Aspose.Words, vous pouvez modifier le style des accents dans un document Word. L'API vous permet d'ajuster les propriétés de style telles que la couleur, la taille, le type de ligne, etc., pour personnaliser l'apparence des marques d'accentuation.

#### Q : Comment puis-je supprimer tous les accents d'un document Word à l'aide d'Aspose.Words ?

R : Pour supprimer toutes les marques d'accent d'un document Word à l'aide de Aspose.Words, vous pouvez utiliser l'API pour parcourir le document, détecter les marques d'accent existantes et les supprimer à l'aide des méthodes appropriées. Cela supprimera toutes les marques d'emphase du document.

#### Q : Puis-je ajouter des accents à une partie spécifique du texte d'un document Word ?

R : Oui, vous pouvez ajouter des accents à une partie spécifique du texte d'un document Word à l'aide d'Aspose.Words. Vous pouvez sélectionner la plage de texte souhaitée à l'aide de l'API et ajouter des marques d'accentuation appropriées à cette partie du texte.

#### Q : Les accents peuvent-ils être personnalisés selon mes besoins ?

R : Oui, les marques d'accent peuvent être personnalisées selon vos besoins à l'aide d'Aspose.Words. Vous pouvez ajuster les propriétés de style des marques d'accentuation, telles que la couleur, la taille, le type de ligne, etc., en fonction de vos préférences de mise en forme.