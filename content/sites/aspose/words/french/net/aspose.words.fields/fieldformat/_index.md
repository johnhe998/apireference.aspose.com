---
title: Class FieldFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fields.FieldFormat classe. Fournit un accès typé au numérique à la date et à lheure et au formatage général du champ.
type: docs
weight: 1790
url: /fr/net/aspose.words.fields/fieldformat/
---
## FieldFormat class

Fournit un accès typé au numérique, à la date et à l'heure et au formatage général du champ.

```csharp
public class FieldFormat
```

## Propriétés

| Nom | La description |
| --- | --- |
| [DateTimeFormat](../../aspose.words.fields/fieldformat/datetimeformat/) { get; set; } | Obtient ou définit une mise en forme appliquée à un résultat de champ de date et d'heure. Correspond au commutateur \@. |
| [GeneralFormats](../../aspose.words.fields/fieldformat/generalformats/) { get; } | Obtient une collection de formats généraux qui sont appliqués à un résultat numérique, textuel ou à n'importe quel champ. Correspond aux commutateurs \*. |
| [NumericFormat](../../aspose.words.fields/fieldformat/numericformat/) { get; set; } | Obtient ou définit une mise en forme appliquée à un résultat de champ numérique. Correspond au commutateur \#. |

### Exemples

Montre comment formater les résultats de champ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Utilisez un générateur de document pour insérer un champ qui affiche un résultat sans format appliqué.
Field field = builder.InsertField("= 2 + 3");

Assert.AreEqual("= 2 + 3", field.GetFieldCode());
Assert.AreEqual("5", field.Result);

// Nous pouvons appliquer un format au résultat d'un champ en utilisant les propriétés du champ.
// Vous trouverez ci-dessous trois types de formats que nous pouvons appliquer au résultat d'un champ.
// 1 - Format numérique :
FieldFormat format = field.Format;
format.NumericFormat = "$###.00";
field.Update();

Assert.AreEqual("= 2 + 3 \\# $###.00", field.GetFieldCode());
Assert.AreEqual("$  5.00", field.Result);

// 2 - Format date/heure :
field = builder.InsertField("DATE");
format = field.Format;
format.DateTimeFormat = "dddd, MMMM dd, yyyy";
field.Update();

Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());
Console.WriteLine($"Today's date, in {format.DateTimeFormat} format:\n\t{field.Result}");

// 3 - Format général :
field = builder.InsertField("= 25 + 33");
format = field.Format;
format.GeneralFormats.Add(GeneralFormat.LowercaseRoman);
format.GeneralFormats.Add(GeneralFormat.Upper);
field.Update();

int index = 0;
using (IEnumerator<GeneralFormat> generalFormatEnumerator = format.GeneralFormats.GetEnumerator())
    while (generalFormatEnumerator.MoveNext())
        Console.WriteLine($"General format index {index++}: {generalFormatEnumerator.Current}");

Assert.AreEqual("= 25 + 33 \\* roman \\* Upper", field.GetFieldCode());
Assert.AreEqual("LVIII", field.Result);
Assert.AreEqual(2, format.GeneralFormats.Count);
Assert.AreEqual(GeneralFormat.LowercaseRoman, format.GeneralFormats[0]);

// Nous pouvons supprimer nos formats pour rétablir le résultat du champ dans sa forme d'origine.
format.GeneralFormats.Remove(GeneralFormat.LowercaseRoman);
format.GeneralFormats.RemoveAt(0);
Assert.AreEqual(0, format.GeneralFormats.Count);
field.Update();

Assert.AreEqual("= 25 + 33  ", field.GetFieldCode());
Assert.AreEqual("58", field.Result);
Assert.AreEqual(0, format.GeneralFormats.Count);
```

### Voir également

* espace de noms [Aspose.Words.Fields](../../aspose.words.fields/)
* Assemblée [Aspose.Words](../../)


