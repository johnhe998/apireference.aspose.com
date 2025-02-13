---
title: TxtLoadOptions.DetectNumberingWithWhitespaces
second_title: Référence de l'API Aspose.Words pour .NET
description: TxtLoadOptions propriété. Permet de spécifier comment les éléments de la liste numérotée sont reconnus lorsquun document est importé à partir dun format texte brut. La valeur par défaut est true.
type: docs
weight: 20
url: /fr/net/aspose.words.loading/txtloadoptions/detectnumberingwithwhitespaces/
---
## TxtLoadOptions.DetectNumberingWithWhitespaces property

Permet de spécifier comment les éléments de la liste numérotée sont reconnus lorsqu'un document est importé à partir d'un format texte brut. La valeur par défaut est true.

```csharp
public bool DetectNumberingWithWhitespaces { get; set; }
```

### Remarques

Si cette option est définie sur false, l'algorithme de reconnaissance des listes détecte les paragraphes de liste, lorsque les numéros de liste se terminent par soit un point, une parenthèse droite ou des symboles de puce (tels que "•", "*", "-" ou "o").

Si cette option est définie sur true, les espaces blancs sont également utilisés comme délimiteurs de numéros de liste : l'algorithme de reconnaissance de liste pour la numérotation de style arabe (1., 1.1.2.) utilise à la fois des espaces blancs et des symboles de point ("".").

### Exemples

Montre comment détecter des listes lors du chargement de documents en texte brut.

```csharp
// Crée un document en clair dans une chaîne avec quatre parties distinctes que nous pouvons interpréter comme des listes,
// avec différents délimiteurs. Lors du chargement du document en clair dans un objet "Document",
// Aspose.Words détectera toujours les trois premières listes et ajoutera un objet "List"
// pour chacun à la propriété "Listes" du document.
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";

// Crée un objet "TxtLoadOptions", que nous pouvons passer au constructeur d'un document
// pour modifier la façon dont nous chargeons un document en clair.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Définissez la propriété "DetectNumberingWithWhitespaces" sur "true" pour détecter les éléments numérotés
// avec des délimiteurs blancs, comme la quatrième liste de notre document, en tant que listes.
// Cela peut également détecter par erreur les paragraphes commençant par des nombres en tant que listes.
// Définissez la propriété "DetectNumberingWithWhitespaces" sur "false"
// pour ne pas créer de listes à partir d'éléments numérotés avec des délimiteurs blancs.
loadOptions.DetectNumberingWithWhitespaces = detectNumberingWithWhitespaces;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

if (detectNumberingWithWhitespaces)
{
    Assert.AreEqual(4, doc.Lists.Count);
    Assert.True(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
else
{
    Assert.AreEqual(3, doc.Lists.Count);
    Assert.False(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
```

### Voir également

* class [TxtLoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../txtloadoptions/)
* Assemblée [Aspose.Words](../../../)


