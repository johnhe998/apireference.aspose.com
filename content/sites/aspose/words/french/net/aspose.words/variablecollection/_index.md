---
title: Class VariableCollection
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.VariableCollection classe. Une collection de variables de document.
type: docs
weight: 6230
url: /fr/net/aspose.words/variablecollection/
---
## VariableCollection class

Une collection de variables de document.

```csharp
public class VariableCollection : IEnumerable<KeyValuePair<string, string>>
```

## Propriétés

| Nom | La description |
| --- | --- |
| [Count](../../aspose.words/variablecollection/count/) { get; } | Obtient le nombre d'éléments contenus dans la collection. |
| [Item](../../aspose.words/variablecollection/item/) { get; set; } | Obtient ou définit une variable de document par le nom insensible à la casse. les valeurs nulles ne sont pas autorisées comme côté droit de l'affectation et seront remplacées par une chaîne vide. (2 indexers) |

## Méthodes

| Nom | La description |
| --- | --- |
| [Add](../../aspose.words/variablecollection/add/)(string, string) | Ajoute une variable de document à la collection. |
| [Clear](../../aspose.words/variablecollection/clear/)() | Supprime tous les éléments de la collection. |
| [Contains](../../aspose.words/variablecollection/contains/)(string) | Détermine si la collection contient une variable de document avec le nom donné. |
| [GetEnumerator](../../aspose.words/variablecollection/getenumerator/)() | Renvoie un objet énumérateur qui peut être utilisé pour itérer sur toutes les variables de la collection. |
| [IndexOfKey](../../aspose.words/variablecollection/indexofkey/)(string) | Renvoie l'index de base zéro de la variable de document spécifiée dans la collection. |
| [Remove](../../aspose.words/variablecollection/remove/)(string) | Supprime une variable de document portant le nom spécifié de la collection. |
| [RemoveAt](../../aspose.words/variablecollection/removeat/)(int) | Supprime une variable de document à l'index spécifié. |

### Remarques

Les noms et les valeurs des variables sont des chaînes.

Les noms de variables ne sont pas sensibles à la casse.

### Exemples

Montre comment travailler avec la collection de variables d'un document.

```csharp
Document doc = new Document();
VariableCollection variables = doc.Variables;

// Chaque document a une collection de variables de paires clé/valeur, auxquelles nous pouvons ajouter des éléments.
variables.Add("Home address", "123 Main St.");
variables.Add("City", "London");
variables.Add("Bedrooms", "3");

Assert.AreEqual(3, variables.Count);

// On peut afficher les valeurs des variables dans le corps du document en utilisant les champs DOCVARIABLE.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocVariable field = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
field.VariableName = "Home address";
field.Update();

Assert.AreEqual("123 Main St.", field.Result);

// L'attribution de valeurs aux clés existantes les mettra à jour.
variables.Add("Home address", "456 Queen St.");

// Nous devrons ensuite mettre à jour les champs DOCVARIABLE pour nous assurer qu'ils affichent une valeur à jour.
Assert.AreEqual("123 Main St.", field.Result);

field.Update();

Assert.AreEqual("456 Queen St.", field.Result);

// Vérifiez que les variables de document avec un certain nom ou une certaine valeur existent.
Assert.True(variables.Contains("City"));
Assert.True(variables.Any(v => v.Value == "London"));

// La collection de variables trie automatiquement les variables par ordre alphabétique de nom.
Assert.AreEqual(0, variables.IndexOfKey("Bedrooms"));
Assert.AreEqual(1, variables.IndexOfKey("City"));
Assert.AreEqual(2, variables.IndexOfKey("Home address"));

// Énumération sur la collection de variables.
using (IEnumerator<KeyValuePair<string, string>> enumerator = doc.Variables.GetEnumerator())
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: {enumerator.Current.Key}, Value: {enumerator.Current.Value}");

// Vous trouverez ci-dessous trois manières de supprimer des variables de document d'une collection.
// 1 - Par nom :
variables.Remove("City");

Assert.False(variables.Contains("City"));

// 2 - Par index :
variables.RemoveAt(1);

Assert.False(variables.Contains("Home address"));

// 3 - Efface toute la collection d'un coup :
variables.Clear();

Assert.That(variables, Is.Empty);
```

### Voir également

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


