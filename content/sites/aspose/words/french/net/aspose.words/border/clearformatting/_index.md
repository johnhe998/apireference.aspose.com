---
title: Border.ClearFormatting
second_title: Référence de l'API Aspose.Words pour .NET
description: Border méthode. Réinitialise les propriétés de bordure aux valeurs par défaut.
type: docs
weight: 70
url: /fr/net/aspose.words/border/clearformatting/
---
## Border.ClearFormatting method

Réinitialise les propriétés de bordure aux valeurs par défaut.

```csharp
public void ClearFormatting()
```

### Remarques

Lorsque les propriétés de bordure sont réinitialisées aux valeurs par défaut, la bordure est invisible.

### Exemples

Montre comment supprimer les bordures d'un paragraphe.

```csharp
Document doc = new Document(MyDir + "Borders.docx");

// Chaque paragraphe a un ensemble individuel de bordures.
// Nous pouvons accéder aux paramètres d'apparence de ces bordures via l'objet format de paragraphe.
BorderCollection borders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;

Assert.AreEqual(Color.Red.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(3.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.Single, borders[0].LineStyle);
Assert.True(borders[0].IsVisible);

// Nous pouvons supprimer une bordure immédiatement en exécutant la méthode ClearFormatting. 
// L'exécution de cette méthode sur chaque bordure d'un paragraphe supprimera toutes ses bordures.
foreach (Border border in borders)
    border.ClearFormatting();

Assert.AreEqual(Color.Empty.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(0.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.None, borders[0].LineStyle);
Assert.IsFalse(borders[0].IsVisible);

doc.Save(ArtifactsDir + "Border.ClearFormatting.docx");
```

### Voir également

* class [Border](../)
* espace de noms [Aspose.Words](../../border/)
* Assemblée [Aspose.Words](../../../)


