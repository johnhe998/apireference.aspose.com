---
title: Class OdsoFieldMapData
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Settings.OdsoFieldMapData classe. Spécifie comment une colonne de la source de données externe doit être mappée aux champs de fusion prédéfinis dans le document.
type: docs
weight: 5600
url: /fr/net/aspose.words.settings/odsofieldmapdata/
---
## OdsoFieldMapData class

Spécifie comment une colonne de la source de données externe doit être mappée aux champs de fusion prédéfinis dans le document.

```csharp
public class OdsoFieldMapData
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [OdsoFieldMapData](odsofieldmapdata/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [Column](../../aspose.words.settings/odsofieldmapdata/column/) { get; set; } | Spécifie l'index de base zéro de la colonne dans une source de données externe qui doit être mappé au nom local d'un champ MERGEFIELD spécifique. La valeur par défaut est 0. |
| [MappedName](../../aspose.words.settings/odsofieldmapdata/mappedname/) { get; set; } | Spécifie le nom de champ de fusion prédéfini qui doit être mappé au numéro de colonne spécifié par le[`Column`](./column/) propriété dans ce mappage de champ. La valeur par défaut est une chaîne vide. |
| [Name](../../aspose.words.settings/odsofieldmapdata/name/) { get; set; } | Spécifie le nom de la colonne dans une source de données externe pour la colonne dont l'index est spécifié par le[`Column`](./column/) propriété. La valeur par défaut est une chaîne vide. |
| [Type](../../aspose.words.settings/odsofieldmapdata/type/) { get; set; } | Spécifie si un champ de publipostage donné a été mappé à une colonne dans la source de données externe donnée ou non. La valeur par défaut estDefault . |

## Méthodes

| Nom | La description |
| --- | --- |
| [Clone](../../aspose.words.settings/odsofieldmapdata/clone/)() | Renvoie un clone profond de cet objet. |

### Remarques

Microsoft Word fournit des noms de champs de fusion prédéfinis qu'il permet d'insérer dans un document en tant que MERGEFIELD ou à utiliser dans les champs ADDRESSBLOCK ou GREETINGLINE. Les informations spécifiées dans`OdsoFieldMapData` permet de mapper une colonne de la source de données externe à un seul champ de fusion prédéfini.

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

* espace de noms [Aspose.Words.Settings](../../aspose.words.settings/)
* Assemblée [Aspose.Words](../../)


