---
title: Enum OdsoFieldMappingType
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Settings.OdsoFieldMappingType énumération. Spécifie les types possibles utilisés pour indiquer si un champ de publipostage donné a été mappé à une colonne dans la source de données externe donnée.
type: docs
weight: 5620
url: /fr/net/aspose.words.settings/odsofieldmappingtype/
---
## OdsoFieldMappingType enumeration

Spécifie les types possibles utilisés pour indiquer si un champ de publipostage donné a été mappé à une colonne dans la source de données externe donnée.

```csharp
public enum OdsoFieldMappingType
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Column | `0` | Spécifie que le champ de fusion et publipostage a été mappé à une colonne dans la source de données externe donnée. |
| Null | `1` | Spécifie que le champ de fusion et publipostage n'a pas été mappé à une colonne dans la source de données externe donnée. |
| Default | `1` | Égal àNull . |

### Exemples

Montre comment accéder à la collection de données qui mappe les colonnes de la source de données aux champs de fusion.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// Cette collection définit comment un publipostage mappera les colonnes d'une source de données
// aux champs prédéfinis MERGEFIELD, ADDRESSBLOCK et GREETINGLINE.
OdsoFieldMapDataCollection dataCollection = doc.MailMergeSettings.Odso.FieldMapDatas;
Assert.AreEqual(30, dataCollection.Count);

using (IEnumerator<OdsoFieldMapData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Field map data index {index++}, type \"{enumerator.Current.Type}\":");

        Console.WriteLine(
            enumerator.Current.Type != OdsoFieldMappingType.Null
                ? $"\tColumn \"{enumerator.Current.Name}\", number {enumerator.Current.Column} mapped to merge field \"{enumerator.Current.MappedName}\"."
                : "\tNo valid column to field mapping data present.");
    }
}

// Clone les éléments de cette collection.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Utilise les éléments de la méthode "RemoveAt" individuellement par index.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// Utilisez la méthode "Clear" pour effacer toute la collection d'un coup.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Voir également

* property [Type](../odsofieldmapdata/type/)
* espace de noms [Aspose.Words.Settings](../../aspose.words.settings/)
* Assemblée [Aspose.Words](../../)


