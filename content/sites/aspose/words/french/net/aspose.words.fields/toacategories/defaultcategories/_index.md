---
title: ToaCategories.DefaultCategories
second_title: Référence de l'API Aspose.Words pour .NET
description: ToaCategories propriété. Obtient la table par défaut des catégories dautorités.
type: docs
weight: 20
url: /fr/net/aspose.words.fields/toacategories/defaultcategories/
---
## ToaCategories.DefaultCategories property

Obtient la table par défaut des catégories d'autorités.

```csharp
public static ToaCategories DefaultCategories { get; }
```

### Remarques

Utilisez le[`ToaCategories`](../../fieldoptions/toacategories/) propriété pour spécifier la table des catégories de références pour un seul document.

### Exemples

Montre comment spécifier un ensemble de catégories pour les champs TOA.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Les champs TOA peuvent filtrer leurs entrées par catégories définies dans cette collection.
ToaCategories toaCategories = new ToaCategories();
doc.FieldOptions.ToaCategories = toaCategories;

// Cette collection de catégories est fournie avec des valeurs par défaut, que nous pouvons remplacer par des valeurs personnalisées.
Assert.AreEqual("Cases", toaCategories[1]);
Assert.AreEqual("Statutes", toaCategories[2]);

toaCategories[1] = "My Category 1";
toaCategories[2] = "My Category 2";

// Nous pouvons toujours accéder aux valeurs par défaut via cette collection.
Assert.AreEqual("Cases", ToaCategories.DefaultCategories[1]);
Assert.AreEqual("Statutes", ToaCategories.DefaultCategories[2]);

// Insérer 2 champs TOA. Les champs TOA créent une entrée pour chaque champ TA dans le document.
// Utilisez le commutateur "\c" pour sélectionner l'index d'une catégorie de notre collection.
// Avec ce commutateur, un champ TOA ne récupèrera que les entrées des champs TA qui
// ont également un commutateur "\c" avec un index de catégorie correspondant. Chaque champ TOA affichera également
// le nom de la catégorie vers laquelle son commutateur "\c" pointe.
builder.InsertField("TOA \\c 1 \\h", null);
builder.InsertField("TOA \\c 2 \\h", null);
builder.InsertBreak(BreakType.PageBreak);

// Insérer des entrées TOA dans 2 catégories. Notre premier champ TOA recevra une entrée,
// du deuxième champ TA dont le commutateur "\c" pointe également vers la première catégorie.
// Le deuxième champ TOA aura deux entrées des deux autres champs TA.
builder.InsertField("TA \\c 2 \\l \"entry 1\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 1 \\l \"entry 2\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 2 \\l \"entry 3\"");

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.TOA.Categories.docx");
```

### Voir également

* class [ToaCategories](../)
* espace de noms [Aspose.Words.Fields](../../toacategories/)
* Assemblée [Aspose.Words](../../../)


