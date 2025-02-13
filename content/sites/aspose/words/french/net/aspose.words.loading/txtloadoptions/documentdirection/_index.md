---
title: TxtLoadOptions.DocumentDirection
second_title: Référence de l'API Aspose.Words pour .NET
description: TxtLoadOptions propriété. Obtient ou définit une direction de document. La valeur par défaut estLeftToRight .
type: docs
weight: 30
url: /fr/net/aspose.words.loading/txtloadoptions/documentdirection/
---
## TxtLoadOptions.DocumentDirection property

Obtient ou définit une direction de document. La valeur par défaut estLeftToRight .

```csharp
public DocumentDirection DocumentDirection { get; set; }
```

### Exemples

Montre comment détecter la direction du texte d'un document en clair.

```csharp
// Crée un objet "TxtLoadOptions", que nous pouvons passer au constructeur d'un document
// pour modifier la façon dont nous chargeons un document en clair.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Définir la propriété "DocumentDirection" sur "DocumentDirection.Auto" détecte automatiquement
// la direction de chaque paragraphe de texte qu'Aspose.Words charge à partir du texte brut.
// La propriété "Bidi" de chaque paragraphe stockera sa direction.
loadOptions.DocumentDirection = DocumentDirection.Auto;

// Détecte le texte hébreu de droite à gauche.
Document doc = new Document(MyDir + "Hebrew text.txt", loadOptions);

Assert.True(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);

// Détecte le texte anglais de droite à gauche.
doc = new Document(MyDir + "English text.txt", loadOptions);

Assert.False(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);
```

### Voir également

* enum [DocumentDirection](../../documentdirection/)
* class [TxtLoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../txtloadoptions/)
* Assemblée [Aspose.Words](../../../)


