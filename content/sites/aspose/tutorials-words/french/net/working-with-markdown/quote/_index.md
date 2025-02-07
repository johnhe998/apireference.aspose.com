---
title: Citation
linktitle: Citation
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser la citation avec Aspose.Words pour .NET Guide étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-markdown/quote/
---

Dans cet exemple, nous expliquerons comment utiliser la fonction de citation avec Aspose.Words for .NET Quote est utilisé pour mettre en évidence des sections de texte en les entourant d'une bordure spéciale.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Utiliser le style de citation par défaut

Nous utiliserons le style de paragraphe par défaut appelé "Citation" pour appliquer la mise en forme des citations au texte.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Étape 3 : Création de styles pour les niveaux imbriqués

 Nous pouvons créer des styles pour les niveaux imbriqués en utilisant le`Styles.Add` méthode de la`Document` objet. Dans cet exemple, nous créons un style appelé "Quote1" pour représenter un niveau de citation imbriqué.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Exemple de code source pour les citations avec Aspose.Words pour .NET


```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Par défaut, un document stocke le style blockquote pour le premier niveau.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Créez des styles pour les niveaux imbriqués grâce à l'héritage de style.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de citations avec Aspose.Words pour .NET.


### FAQ

#### Q : Qu'est-ce qu'une citation dans Markdown ?

R : Une citation dans Markdown est un moyen de mettre en évidence des passages de texte provenant d'autres sources ou de faire référence à des citations célèbres.

#### Q : Comment utiliser les guillemets dans Markdown ?

R : Pour utiliser une citation dans Markdown, placez le texte de la citation entre crochets (`>`). Chaque ligne de la citation doit commencer par un chevron.

#### Q : Les guillemets Markdown prennent-ils en charge les attributs ?

R : Les citations Markdown ne prennent pas en charge des attributs spécifiques. Ils sont simplement mis en évidence par la mise en forme du texte cité.

#### Q : Pouvez-vous intégrer des guillemets dans Markdown ?

R : Oui, il est possible d'imbriquer les guillemets dans Markdown en ajoutant un niveau supplémentaire de crochets angulaires (`>`).