---
title: FootnoteOptions.Position
second_title: Référence de l'API Aspose.Words pour .NET
description: FootnoteOptions propriété. Spécifie la position des notes de bas de page.
type: docs
weight: 30
url: /fr/net/aspose.words.notes/footnoteoptions/position/
---
## FootnoteOptions.Position property

Spécifie la position des notes de bas de page.

```csharp
public FootnotePosition Position { get; set; }
```

### Exemples

Montre comment sélectionner un endroit différent où le document rassemble et affiche ses notes de bas de page.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Une note de bas de page est un moyen d'attacher une référence ou un commentaire latéral au texte
// qui n'interfère pas avec le flux du corps du texte principal.  
// L'insertion d'une note de bas de page ajoute un petit symbole de référence en exposant
// au corps du texte principal où nous insérons la note de bas de page.
// Chaque note de bas de page crée également une entrée en bas de page, constituée d'un symbole
// qui correspond au symbole de référence dans le corps du texte principal.
// Le texte de référence que nous transmettons à la méthode "InsertFootnote" du générateur de document.
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote contents.");

// Nous pouvons utiliser la propriété "Position" pour déterminer où le document placera toutes ses notes de bas de page.
// Si nous définissons la valeur de la propriété "Position" sur "FootnotePosition.BottomOfPage",
// chaque note de bas de page apparaîtra au bas de la page qui contient sa marque de référence. Ceci est la valeur par défault.
// Si nous définissons la valeur de la propriété "Position" sur "FootnotePosition.BeneathText",
// chaque note de bas de page apparaîtra à la fin du texte de la page qui contient sa marque de référence.
doc.FootnoteOptions.Position = footnotePosition;

doc.Save(ArtifactsDir + "InlineStory.PositionFootnote.docx");
```

### Voir également

* enum [FootnotePosition](../../footnoteposition/)
* class [FootnoteOptions](../)
* espace de noms [Aspose.Words.Notes](../../footnoteoptions/)
* Assemblée [Aspose.Words](../../../)


