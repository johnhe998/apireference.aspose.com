---
title: FieldIndex.RunSubentriesOnSameLine
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldIndex propriété. Obtient ou définit si les sousentrées sont exécutées sur la même ligne que lentrée principale.
type: docs
weight: 140
url: /fr/net/aspose.words.fields/fieldindex/runsubentriesonsameline/
---
## FieldIndex.RunSubentriesOnSameLine property

Obtient ou définit si les sous-entrées sont exécutées sur la même ligne que l'entrée principale.

```csharp
public bool RunSubentriesOnSameLine { get; set; }
```

### Exemples

Montre comment travailler avec des sous-entrées dans un champ INDEX.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée un champ INDEX qui affichera une entrée pour chaque champ XE trouvé dans le document.
// Chaque entrée affichera la valeur de la propriété Text du champ XE sur le côté gauche,
// et le numéro de la page qui contient le champ XE à droite.
// L'entrée INDEX collectera tous les champs XE avec des valeurs correspondantes dans la propriété "Texte"
// en une seule entrée au lieu de créer une entrée pour chaque champ XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.PageNumberSeparator = ", see page ";
index.Heading = "A";

// Champs XE qui ont une propriété Text dont la valeur devient l'en-tête de l'entrée INDEX.
// Si cette valeur contient deux segments de chaîne séparés par deux-points (l'entrée INDEX traitera le délimiteur :) ,
// le premier segment est le titre, et le second segment deviendra le sous-titre.
// Le champ INDEX regroupe d'abord les entrées par ordre alphabétique, puis, s'il y a plusieurs champs XE avec le même
// en-têtes, le champ INDEX les sous-groupera davantage par les valeurs de ces en-têtes.
// Il peut y avoir plusieurs couches de sous-groupes, selon le nombre de fois
// les propriétés Text des champs XE sont segmentées comme ceci.
 // Par défaut, un groupe de saisie de champ INDEX créera une nouvelle ligne pour chaque sous-titre de ce groupe.
// Nous pouvons définir le drapeau RunSubentriesOnSameLine sur true pour conserver l'en-tête,
// et chaque sous-titre du groupe sur une seule ligne à la place, ce qui rendra le champ INDEX plus compact.
index.RunSubentriesOnSameLine = runSubentriesOnTheSameLine;

if (runSubentriesOnTheSameLine)
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A \\r", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A", index.GetFieldCode());

// Insère deux champs XE, chacun sur une nouvelle page, et avec le même titre nommé "Titre 1",
// que le champ INDEX utilisera pour les regrouper.
// Si RunSubentriesOnSameLine est faux, alors la table INDEX créera trois lignes :
// une ligne pour le titre de regroupement "Titre 1", et une ligne supplémentaire pour chaque sous-titre.
// Si RunSubentriesOnSameLine est vrai, alors la table INDEX créera une ligne
// entrée qui englobe le titre et chaque sous-titre.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 1";

Assert.AreEqual(" XE  \"Heading 1:Subheading 1\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 2";

doc.UpdateFields();
doc.Save(ArtifactsDir + $"Field.INDEX.XE.Subheading.docx");
```

### Voir également

* class [FieldIndex](../)
* espace de noms [Aspose.Words.Fields](../../fieldindex/)
* Assemblée [Aspose.Words](../../../)


