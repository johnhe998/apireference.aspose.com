---
title: Enum FootnotePosition
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Notes.FootnotePosition énumération. Définit la position de la note de bas de page.
type: docs
weight: 4050
url: /fr/net/aspose.words.notes/footnoteposition/
---
## FootnotePosition enumeration

Définit la position de la note de bas de page.

```csharp
public enum FootnotePosition
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| BottomOfPage | `1` | Les notes de bas de page sont affichées au bas de chaque page. |
| BeneathText | `2` | Les notes de bas de page sont affichées sous le texte de chaque page. |

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

* class [FootnoteOptions](../footnoteoptions/)
* espace de noms [Aspose.Words.Notes](../../aspose.words.notes/)
* Assemblée [Aspose.Words](../../)


