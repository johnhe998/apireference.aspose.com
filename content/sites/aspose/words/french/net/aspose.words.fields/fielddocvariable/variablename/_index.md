---
title: FieldDocVariable.VariableName
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldDocVariable propriété. Obtient ou définit le nom de la variable de document à récupérer.
type: docs
weight: 20
url: /fr/net/aspose.words.fields/fielddocvariable/variablename/
---
## FieldDocVariable.VariableName property

Obtient ou définit le nom de la variable de document à récupérer.

```csharp
public string VariableName { get; set; }
```

### Exemples

Montre comment utiliser les champs DOCPROPERTY pour afficher les propriétés et les variables du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vous trouverez ci-dessous deux manières d'utiliser les champs DOCPROPERTY.
// 1 - Affiche une propriété intégrée :
// Définissez une valeur personnalisée pour la propriété intégrée "Catégorie", puis insérez un champ DOCPROPERTY qui y fait référence.
doc.BuiltInDocumentProperties.Category = "My category";

FieldDocProperty fieldDocProperty = (FieldDocProperty)builder.InsertField(" DOCPROPERTY Category ");
fieldDocProperty.Update();

Assert.AreEqual(" DOCPROPERTY Category ", fieldDocProperty.GetFieldCode());
Assert.AreEqual("My category", fieldDocProperty.Result);

builder.InsertParagraph();

// 2 - Affichez une variable de document personnalisée :
// Définissez une variable personnalisée, puis référencez cette variable avec un champ DOCPROPERTY.
Assert.That(doc.Variables, Is.Empty);
doc.Variables.Add("My variable", "My variable's value");

FieldDocVariable fieldDocVariable = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
fieldDocVariable.VariableName = "My Variable";
fieldDocVariable.Update();

Assert.AreEqual(" DOCVARIABLE  \"My Variable\"", fieldDocVariable.GetFieldCode());
Assert.AreEqual("My variable's value", fieldDocVariable.Result);

doc.Save(ArtifactsDir + "Field.DOCPROPERTY.DOCVARIABLE.docx");
```

### Voir également

* class [FieldDocVariable](../)
* espace de noms [Aspose.Words.Fields](../../fielddocvariable/)
* Assemblée [Aspose.Words](../../../)


