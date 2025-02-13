---
title: Field.Result
second_title: Référence de l'API Aspose.Words pour .NET
description: Field propriété. Obtient ou définit le texte qui se trouve entre le séparateur de champ et la fin du champ.
type: docs
weight: 70
url: /fr/net/aspose.words.fields/field/result/
---
## Field.Result property

Obtient ou définit le texte qui se trouve entre le séparateur de champ et la fin du champ.

```csharp
public string Result { get; set; }
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

* class [Field](../)
* espace de noms [Aspose.Words.Fields](../../field/)
* Assemblée [Aspose.Words](../../../)


