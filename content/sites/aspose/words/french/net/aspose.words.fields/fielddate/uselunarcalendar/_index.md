---
title: FieldDate.UseLunarCalendar
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldDate propriété. Obtient ou définit sil faut utiliser le calendrier Hijri Lunar ou Hebrew Lunar.
type: docs
weight: 30
url: /fr/net/aspose.words.fields/fielddate/uselunarcalendar/
---
## FieldDate.UseLunarCalendar property

Obtient ou définit s'il faut utiliser le calendrier Hijri Lunar ou Hebrew Lunar.

```csharp
public bool UseLunarCalendar { get; set; }
```

### Exemples

Montre comment utiliser les champs DATE pour afficher les dates selon différents types de calendriers.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Si nous voulons que le texte du document affiche toujours la date correcte, nous pouvons utiliser un champ DATE.
// Vous trouverez ci-dessous trois types de calendriers culturels qu'un champ DATE peut utiliser pour afficher une date.
// 1 - Calendrier lunaire islamique :
FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLunarCalendar = true;
Assert.AreEqual(" DATE  \\h", field.GetFieldCode());
builder.Writeln();

// 2 - Calendrier Umm al-Qura :
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseUmAlQuraCalendar = true;
Assert.AreEqual(" DATE  \\u", field.GetFieldCode());
builder.Writeln();

// 3 - Calendrier national indien :
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseSakaEraCalendar = true;
Assert.AreEqual(" DATE  \\s", field.GetFieldCode());
builder.Writeln();

// Insérez un champ DATE et définissez son type de calendrier sur celui utilisé en dernier par l'application hôte.
// Dans Microsoft Word, le type sera le dernier utilisé dans Insert -> Texte -> Boîte de dialogue Date et heure.
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLastFormat = true;
Assert.AreEqual(" DATE  \\l", field.GetFieldCode());
builder.Writeln();

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATE.docx");
```

### Voir également

* class [FieldDate](../)
* espace de noms [Aspose.Words.Fields](../../fielddate/)
* Assemblée [Aspose.Words](../../../)


