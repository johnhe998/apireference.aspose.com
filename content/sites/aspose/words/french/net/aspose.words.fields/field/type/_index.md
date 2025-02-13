---
title: Field.Type
second_title: Référence de l'API Aspose.Words pour .NET
description: Field propriété. Obtient le type de champ Microsoft Word.
type: docs
weight: 100
url: /fr/net/aspose.words.fields/field/type/
---
## Field.Type property

Obtient le type de champ Microsoft Word.

```csharp
public virtual FieldType Type { get; }
```

### Exemples

Montre comment insérer un champ dans un document à l'aide d'un code de champ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE \\@ \"dddd, MMMM dd, yyyy\"");

Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// Cette surcharge de la méthode InsertField met automatiquement à jour les champs insérés.
Assert.That(DateTime.Parse(field.Result), Is.EqualTo(DateTime.Today).Within(1).Days);
```

### Voir également

* enum [FieldType](../../fieldtype/)
* class [Field](../)
* espace de noms [Aspose.Words.Fields](../../field/)
* Assemblée [Aspose.Words](../../../)


