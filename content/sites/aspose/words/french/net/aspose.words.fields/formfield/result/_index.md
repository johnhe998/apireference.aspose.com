---
title: FormField.Result
second_title: Référence de l'API Aspose.Words pour .NET
description: FormField propriété. Obtient ou définit une chaîne qui représente le résultat de ce champ de formulaire.
type: docs
weight: 170
url: /fr/net/aspose.words.fields/formfield/result/
---
## FormField.Result property

Obtient ou définit une chaîne qui représente le résultat de ce champ de formulaire.

```csharp
public string Result { get; set; }
```

### Remarques

Pour un champ de formulaire texte, le résultat est le texte qui se trouve dans le champ.

Pour un champ de formulaire de case à cocher, le résultat peut être "1" ou "0" pour indiquer coché ou non coché.

Pour un champ de formulaire déroulant, le résultat est la chaîne sélectionnée dans la liste déroulante.

Paramètre`Result` pour un champ de formulaire texte n'applique pas le format de texte spécifié dans[`TextInputFormat`](../textinputformat/) . Si vous souhaitez définir une valeur et appliquer le format , utilisez le[`SetTextInputValue`](../settextinputvalue/) méthode.

Pour un champ de formulaire texte, le[`TextInputDefault`](../textinputdefault/) la valeur est appliquée si*value* est`nul`.

### Exemples

Montre comment insérer une zone de liste déroulante.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Insère une zone de liste déroulante qui permettra à un utilisateur de choisir une option parmi une collection de chaînes.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

Assert.AreEqual("MyComboBox", comboBox.Name);
Assert.AreEqual(FieldType.FieldFormDropDown, comboBox.Type);
Assert.AreEqual("Apple", comboBox.Result);

// Le champ du formulaire apparaîtra sous la forme d'une balise html "select".
doc.Save(ArtifactsDir + "FormFields.Create.html");
```

### Voir également

* class [FormField](../)
* espace de noms [Aspose.Words.Fields](../../formfield/)
* Assemblée [Aspose.Words](../../../)


