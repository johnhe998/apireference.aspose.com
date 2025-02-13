---
title: BookmarksOutlineLevelCollection.Item
second_title: Référence de l'API Aspose.Words pour .NET
description: BookmarksOutlineLevelCollection propriété. Obtient ou définit un niveau hiérarchique de signet par le nom du signet.
type: docs
weight: 30
url: /fr/net/aspose.words.saving/bookmarksoutlinelevelcollection/item/
---
## BookmarksOutlineLevelCollection indexer (1 of 2)

Obtient ou définit un niveau hiérarchique de signet par le nom du signet.

```csharp
public int this[string name] { get; set; }
```

| Paramètre | La description |
| --- | --- |
| name | Nom du signet insensible à la casse. |

### Return_Value

Niveau hiérarchique du signet. La plage valide est de 0 à 9.

### Exemples

Montre comment définir des niveaux hiérarchiques pour les signets.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère un signet avec un autre signet imbriqué à l'intérieur.
builder.StartBookmark("Bookmark 1");
builder.Writeln("Text inside Bookmark 1.");

builder.StartBookmark("Bookmark 2");
builder.Writeln("Text inside Bookmark 1 and 2.");
builder.EndBookmark("Bookmark 2");

builder.Writeln("Text inside Bookmark 1.");
builder.EndBookmark("Bookmark 1");

// Insérer un autre signet.
builder.StartBookmark("Bookmark 3");
builder.Writeln("Text inside Bookmark 3.");
builder.EndBookmark("Bookmark 3");

// Lors de l'enregistrement au format .pdf, les signets sont accessibles via un menu déroulant et utilisés comme ancres par la plupart des lecteurs.
// Les signets peuvent également avoir des valeurs numériques pour les niveaux hiérarchiques,
// activation des entrées de plan de niveau inférieur pour masquer les entrées enfants de niveau supérieur lorsqu'elles sont réduites dans le lecteur.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
BookmarksOutlineLevelCollection outlineLevels = pdfSaveOptions.OutlineOptions.BookmarksOutlineLevels;

outlineLevels.Add("Bookmark 1", 1);
outlineLevels.Add("Bookmark 2", 2);
outlineLevels.Add("Bookmark 3", 3);

Assert.AreEqual(3, outlineLevels.Count);
Assert.True(outlineLevels.Contains("Bookmark 1"));
Assert.AreEqual(1, outlineLevels[0]);
Assert.AreEqual(2, outlineLevels["Bookmark 2"]);
Assert.AreEqual(2, outlineLevels.IndexOfKey("Bookmark 3"));

// Nous pouvons supprimer deux éléments afin qu'il ne reste que la désignation de niveau hiérarchique pour "Signet 1".
outlineLevels.RemoveAt(2);
outlineLevels.Remove("Bookmark 2");

// Il existe neuf niveaux hiérarchiques. Leur numérotation sera optimisée lors de l'opération de sauvegarde.
// Dans ce cas, les niveaux "5" et "9" deviendront "2" et "3".
outlineLevels.Add("Bookmark 2", 5);
outlineLevels.Add("Bookmark 3", 9);

doc.Save(ArtifactsDir + "BookmarksOutlineLevelCollection.BookmarkLevels.pdf", pdfSaveOptions);

// Vider cette collection conservera les signets et les placera tous au même niveau hiérarchique.
outlineLevels.Clear();
```

### Voir également

* class [BookmarksOutlineLevelCollection](../)
* espace de noms [Aspose.Words.Saving](../../bookmarksoutlinelevelcollection/)
* Assemblée [Aspose.Words](../../../)

---

## BookmarksOutlineLevelCollection indexer (2 of 2)

Obtient ou définit un niveau hiérarchique de signet à l'index spécifié.

```csharp
public int this[int index] { get; set; }
```

| Paramètre | La description |
| --- | --- |
| index | Index de base zéro du signet. |

### Return_Value

Niveau hiérarchique du signet. La plage valide est de 0 à 9.

### Exemples

Montre comment définir des niveaux hiérarchiques pour les signets.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère un signet avec un autre signet imbriqué à l'intérieur.
builder.StartBookmark("Bookmark 1");
builder.Writeln("Text inside Bookmark 1.");

builder.StartBookmark("Bookmark 2");
builder.Writeln("Text inside Bookmark 1 and 2.");
builder.EndBookmark("Bookmark 2");

builder.Writeln("Text inside Bookmark 1.");
builder.EndBookmark("Bookmark 1");

// Insérer un autre signet.
builder.StartBookmark("Bookmark 3");
builder.Writeln("Text inside Bookmark 3.");
builder.EndBookmark("Bookmark 3");

// Lors de l'enregistrement au format .pdf, les signets sont accessibles via un menu déroulant et utilisés comme ancres par la plupart des lecteurs.
// Les signets peuvent également avoir des valeurs numériques pour les niveaux hiérarchiques,
// activation des entrées de plan de niveau inférieur pour masquer les entrées enfants de niveau supérieur lorsqu'elles sont réduites dans le lecteur.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
BookmarksOutlineLevelCollection outlineLevels = pdfSaveOptions.OutlineOptions.BookmarksOutlineLevels;

outlineLevels.Add("Bookmark 1", 1);
outlineLevels.Add("Bookmark 2", 2);
outlineLevels.Add("Bookmark 3", 3);

Assert.AreEqual(3, outlineLevels.Count);
Assert.True(outlineLevels.Contains("Bookmark 1"));
Assert.AreEqual(1, outlineLevels[0]);
Assert.AreEqual(2, outlineLevels["Bookmark 2"]);
Assert.AreEqual(2, outlineLevels.IndexOfKey("Bookmark 3"));

// Nous pouvons supprimer deux éléments afin qu'il ne reste que la désignation de niveau hiérarchique pour "Signet 1".
outlineLevels.RemoveAt(2);
outlineLevels.Remove("Bookmark 2");

// Il existe neuf niveaux hiérarchiques. Leur numérotation sera optimisée lors de l'opération de sauvegarde.
// Dans ce cas, les niveaux "5" et "9" deviendront "2" et "3".
outlineLevels.Add("Bookmark 2", 5);
outlineLevels.Add("Bookmark 3", 9);

doc.Save(ArtifactsDir + "BookmarksOutlineLevelCollection.BookmarkLevels.pdf", pdfSaveOptions);

// Vider cette collection conservera les signets et les placera tous au même niveau hiérarchique.
outlineLevels.Clear();
```

### Voir également

* class [BookmarksOutlineLevelCollection](../)
* espace de noms [Aspose.Words.Saving](../../bookmarksoutlinelevelcollection/)
* Assemblée [Aspose.Words](../../../)


