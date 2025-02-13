---
title: DocumentBuilder.EndColumnBookmark
second_title: Référence de l'API Aspose.Words pour .NET
description: DocumentBuilder méthode. Marque la position actuelle dans le document en tant que fin de signet de colonne. La position doit être dans une cellule du tableau.
type: docs
weight: 200
url: /fr/net/aspose.words/documentbuilder/endcolumnbookmark/
---
## DocumentBuilder.EndColumnBookmark method

Marque la position actuelle dans le document en tant que fin de signet de colonne. La position doit être dans une cellule du tableau.

```csharp
public BookmarkEnd EndColumnBookmark(string bookmarkName)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| bookmarkName | String | Nom du signet. |

### Return_Value

Le nœud de fin de signet qui vient d'être créé.

### Remarques

Un signet de colonne couvre une ou plusieurs colonnes dans une plage de lignes. Pour créer un signet valide, vous devez appeler les deux[`StartColumnBookmark`](../startcolumnbookmark/) et`EndColumnBookmark` avec le même  **bookmarkName** paramètre.

Les signets mal formés ou les signets avec des noms en double seront ignorés lors de l'enregistrement du document.

La position réelle de l'insertion[`BookmarkEnd`](../../bookmarkend/) node peut différer de la position actuelle du document builder.

### Exemples

Montre comment créer un signet de colonne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

builder.InsertCell();
// Les cellules 1,2,4,5 seront mises en signet.
builder.StartColumnBookmark("MyBookmark_1");
// Les signets mal formés ou les signets avec des noms en double seront ignorés lors de l'enregistrement du document.
builder.StartColumnBookmark("MyBookmark_1");
builder.StartColumnBookmark("BadStartBookmark");
builder.Write("Cell 1");

builder.InsertCell();
builder.Write("Cell 2");

builder.InsertCell();
builder.Write("Cell 3");

builder.EndRow();

builder.InsertCell();
builder.Write("Cell 4");

builder.InsertCell();
builder.Write("Cell 5");
builder.EndColumnBookmark("MyBookmark_1");
builder.EndColumnBookmark("MyBookmark_1");

builder.InsertCell();
builder.Write("Cell 6");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "Bookmarks.CreateColumnBookmark.docx");
```

### Voir également

* class [BookmarkEnd](../../bookmarkend/)
* class [DocumentBuilder](../)
* espace de noms [Aspose.Words](../../documentbuilder/)
* Assemblée [Aspose.Words](../../../)


