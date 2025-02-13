---
title: Définir les options de note de fin
linktitle: Définir les options de note de fin
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir les options de note de fin dans les documents Word à l'aide d'Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/working-with-footnote-and-endnote/set-endnote-options/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour définir les options de note de fin dans un document Word. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document source :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Étape 2 : Initialisation de l'objet DocumentBuilder

 Ensuite, initialisez le`DocumentBuilder` objet pour effectuer des opérations sur le document :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Ajouter du texte et une note de fin

 Utilisez le`Write` méthode de la`DocumentBuilder` objet pour ajouter du texte au document, et l'objet`InsertFootnote` méthode pour insérer une note de fin :

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Étape 4 : Définition des options de note de fin

 Accéder au`EndnoteOptions` propriété du document pour modifier les options de note de fin. Dans cet exemple, nous définissons la règle de redémarrage pour redémarrer sur chaque page et la position à la fin de la section :

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Étape 5 : Enregistrer le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

C'est ça! Vous avez défini avec succès les options de note de fin dans un document Word à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Définir les options de note de fin à l'aide de Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je styliser les notes de fin dans Aspose.Words ?

 A: Pour styliser les notes de fin dans Aspose.Words, vous pouvez utiliser le`EndnoteOptions` classe et la`SeparatorNoteTextStyle` propriété. Vous pouvez spécifier le style de police, la taille, la couleur, etc. pour les notes de fin à l'aide de cette propriété.

#### Q : Est-il possible de personnaliser la numérotation des notes de fin dans un document ?

 R : Oui, il est possible de personnaliser la numérotation des notes de fin dans un document. Vous pouvez utiliser le`RestartRule` et`NumberStyle` propriétés de la`EndnoteOptions` class pour définir des règles de redémarrage et des styles de numérotation spécifiques.

#### Q : Comment positionner les notes de fin dans un document ?

 R : Pour positionner les notes de fin dans un document, vous pouvez utiliser le`Position`propriété de la`EndnoteOptions` classe. Vous pouvez spécifier si les notes de fin doivent être placées au bas de chaque page, à la fin de chaque section ou à la fin du document.

#### Q : Puis-je personnaliser le format de numérotation des notes de fin ?

 R : Oui, vous pouvez personnaliser le format de numérotation des notes de fin dans Aspose.Words. Utilisez le`NumberFormat`propriété de la`EndnoteOptions` class pour définir le format souhaité, tel que les chiffres arabes, les chiffres romains, les lettres, etc.

#### Q : Est-il possible de continuer la numérotation des notes de fin entre les sections d'un document ?

 R : Oui, il est possible de continuer la numérotation des notes de fin entre les sections d'un document. Utilisez le`RestartRule`propriété de la`EndnoteOptions` classe et réglez-le sur`RestartContinuous` pour permettre à la numérotation de continuer entre les sections.