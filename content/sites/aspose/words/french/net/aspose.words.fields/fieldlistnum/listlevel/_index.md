---
title: FieldListNum.ListLevel
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldListNum propriété. Obtient ou définit le niveau dans la liste remplaçant le comportement par défaut du champ.
type: docs
weight: 30
url: /fr/net/aspose.words.fields/fieldlistnum/listlevel/
---
## FieldListNum.ListLevel property

Obtient ou définit le niveau dans la liste, remplaçant le comportement par défaut du champ.

```csharp
public string ListLevel { get; set; }
```

### Exemples

Montre comment numéroter des paragraphes avec des champs LISTNUM.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Les champs LISTNUM affichent un nombre qui s'incrémente à chaque champ LISTNUM.
// Ces champs ont également une variété d'options qui nous permettent de les utiliser pour émuler des listes numérotées.
FieldListNum field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);

// Les listes commencent à compter à 1 par défaut, mais nous pouvons définir ce nombre sur une valeur différente, telle que 0.
// Ce champ affichera "0)".
field.StartingNumber = "0";
builder.Writeln("Paragraph 1");

Assert.AreEqual(" LISTNUM  \\s 0", field.GetFieldCode());

 // Les champs LISTNUM conservent des décomptes séparés pour chaque niveau de liste.
// Insertion d'un champ LISTNUM dans le même paragraphe qu'un autre champ LISTNUM
// augmente le niveau de la liste au lieu du nombre.
// Le champ suivant continuera le décompte que nous avons commencé ci-dessus et affichera une valeur de "1" au niveau de liste 1.
builder.InsertField(FieldType.FieldListNum, true);

// Ce champ commencera un décompte au niveau 2 de la liste. Il affichera une valeur de "1".
builder.InsertField(FieldType.FieldListNum, true);

// Ce champ commencera un décompte au niveau 3 de la liste. Il affichera une valeur de "1".
// Différents niveaux de liste ont un formatage différent,
// donc ces champs combinés afficheront une valeur de "1)a)i)".
builder.InsertField(FieldType.FieldListNum, true);
builder.Writeln("Paragraph 2");

// Le prochain champ LISTNUM que nous insérons continuera le décompte au niveau de la liste
// que le champ LISTNUM précédent était activé.
// Nous pouvons utiliser la propriété "ListLevel" pour passer à un niveau de liste différent.
// Si ce champ LISTNUM restait au niveau 3 de la liste, il afficherait "ii)",
// mais, puisque nous l'avons déplacé au niveau 2 de la liste, il continue le décompte à ce niveau et affiche "b)".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListLevel = "2";
builder.Writeln("Paragraph 3");

Assert.AreEqual(" LISTNUM  \\l 2", field.GetFieldCode());

// Nous pouvons définir la propriété ListName pour que le champ émule un autre type de champ AUTONUM.
// "NumberDefault" émule AUTONUM, "OutlineDefault" émule AUTONUMOUT,
// et "LegalDefault" émule les champs AUTONUMLGL.
// Le nom de la liste "OutlineDefault" avec 1 comme numéro de départ entraînera l'affichage de "I.".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.StartingNumber = "1";
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 4");

Assert.IsTrue(field.HasListName);
Assert.AreEqual(" LISTNUM  OutlineDefault \\s 1", field.GetFieldCode());

// Le ListName n'est pas reporté du champ précédent, nous devrons donc le définir pour chaque nouveau champ.
// Ce champ continue le décompte avec le nom de liste différent et affiche "II.".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 5");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.LISTNUM.docx");
```

### Voir également

* class [FieldListNum](../)
* espace de noms [Aspose.Words.Fields](../../fieldlistnum/)
* Assemblée [Aspose.Words](../../../)


