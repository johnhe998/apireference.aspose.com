---
title: FindReplaceOptions.SmartParagraphBreakReplacement
second_title: Référence de l'API Aspose.Words pour .NET
description: FindReplaceOptions propriété. Obtient ou définit une valeur booléenne indiquant quil est autorisé à remplacer le paragraphe break lorsquil ny a pas de paragraphe frère suivant.
type: docs
weight: 140
url: /fr/net/aspose.words.replacing/findreplaceoptions/smartparagraphbreakreplacement/
---
## FindReplaceOptions.SmartParagraphBreakReplacement property

Obtient ou définit une valeur booléenne indiquant qu'il est autorisé à remplacer le paragraphe break lorsqu'il n'y a pas de paragraphe frère suivant.

La valeur par défaut est`faux`.

```csharp
public bool SmartParagraphBreakReplacement { get; set; }
```

### Remarques

Cette option permet de remplacer le saut de paragraphe lorsqu'il n'y a pas de paragraphe frère suivant vers lequel tous les nœuds child peuvent être déplacés, en trouvant tout paragraphe suivant (pas nécessairement frère) après le paragraphe remplacé.

### Exemples

Montre comment supprimer un paragraphe d'une cellule de tableau avec un tableau imbriqué.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée un tableau avec un paragraphe et un tableau intérieur dans la première cellule.
builder.StartTable();
builder.InsertCell();
builder.Write("TEXT1");
builder.StartTable();
builder.InsertCell();
builder.EndTable();
builder.EndTable();
builder.Writeln();

FindReplaceOptions options = new FindReplaceOptions();
// Lorsque l'option suivante est définie sur 'true', Aspose.Words supprimera le texte du paragraphe
// complètement avec sa marque de paragraphe. Sinon, Aspose.Words imitera Word et supprimera
// uniquement le texte du paragraphe et laisse la marque de paragraphe intacte (lorsqu'un tableau suit le texte).
options.SmartParagraphBreakReplacement = isSmartParagraphBreakReplacement;
doc.Range.Replace(new Regex(@"TEXT1&p"), "", options);

doc.Save(ArtifactsDir + "Table.RemoveParagraphTextAndMark.docx");
```

### Voir également

* class [FindReplaceOptions](../)
* espace de noms [Aspose.Words.Replacing](../../findreplaceoptions/)
* Assemblée [Aspose.Words](../../../)


