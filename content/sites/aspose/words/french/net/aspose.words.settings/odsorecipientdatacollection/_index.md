---
title: Class OdsoRecipientDataCollection
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Settings.OdsoRecipientDataCollection classe. Une collection typée deOdsoRecipientData
type: docs
weight: 5640
url: /fr/net/aspose.words.settings/odsorecipientdatacollection/
---
## OdsoRecipientDataCollection class

Une collection typée de[`OdsoRecipientData`](../odsorecipientdata/)

```csharp
public class OdsoRecipientDataCollection : IEnumerable<OdsoRecipientData>
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [OdsoRecipientDataCollection](odsorecipientdatacollection/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [Count](../../aspose.words.settings/odsorecipientdatacollection/count/) { get; } | Obtient le nombre d'éléments contenus dans la collection. |
| [Item](../../aspose.words.settings/odsorecipientdatacollection/item/) { get; set; } | Obtient ou définit un élément de cette collection. |

## Méthodes

| Nom | La description |
| --- | --- |
| [Add](../../aspose.words.settings/odsorecipientdatacollection/add/)(OdsoRecipientData) | Ajoute un objet à la fin de cette collection. |
| [Clear](../../aspose.words.settings/odsorecipientdatacollection/clear/)() | Supprime tous les éléments de cette collection. |
| [GetEnumerator](../../aspose.words.settings/odsorecipientdatacollection/getenumerator/)() | Renvoie un objet énumérateur qui peut être utilisé pour itérer sur tous les éléments de la collection. |
| [RemoveAt](../../aspose.words.settings/odsorecipientdatacollection/removeat/)(int) | Supprime l'élément à l'index spécifié. |

### Exemples

Montre comment accéder à la collection de données qui désigne les enregistrements de source de données de fusion qu'un publipostage exclura.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

OdsoRecipientDataCollection dataCollection = doc.MailMergeSettings.Odso.RecipientDatas;

Assert.AreEqual(70, dataCollection.Count);

using (IEnumerator<OdsoRecipientData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine(
            $"Odso recipient data index {index++} will {(enumerator.Current.Active ? "" : "not ")}be imported upon mail merge.");
        Console.WriteLine($"\tColumn #{enumerator.Current.Column}");
        Console.WriteLine($"\tHash code: {enumerator.Current.Hash}");
        Console.WriteLine($"\tContents array length: {enumerator.Current.UniqueTag.Length}");
    }
}

// Nous pouvons cloner les éléments de cette collection.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Nous pouvons également supprimer des éléments individuellement ou effacer toute la collection en une seule fois.
dataCollection.RemoveAt(0);

Assert.AreEqual(69, dataCollection.Count);

dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Voir également

* class [OdsoRecipientData](../odsorecipientdata/)
* espace de noms [Aspose.Words.Settings](../../aspose.words.settings/)
* Assemblée [Aspose.Words](../../)


