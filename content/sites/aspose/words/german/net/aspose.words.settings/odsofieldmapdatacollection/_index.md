---
title: Class OdsoFieldMapDataCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Settings.OdsoFieldMapDataCollection klas. Eine getippte Sammlung derOdsoFieldMapData Objekte.
type: docs
weight: 5610
url: /de/net/aspose.words.settings/odsofieldmapdatacollection/
---
## OdsoFieldMapDataCollection class

Eine getippte Sammlung der[`OdsoFieldMapData`](../odsofieldmapdata/) Objekte.

```csharp
public class OdsoFieldMapDataCollection : IEnumerable<OdsoFieldMapData>
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [OdsoFieldMapDataCollection](odsofieldmapdatacollection/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words.settings/odsofieldmapdatacollection/count/) { get; } | Ruft die Anzahl der in der Sammlung enthaltenen Elemente ab. |
| [Item](../../aspose.words.settings/odsofieldmapdatacollection/item/) { get; set; } | Ruft ein Element in dieser Sammlung ab oder legt es fest. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Add](../../aspose.words.settings/odsofieldmapdatacollection/add/)(OdsoFieldMapData) | Fügt ein Objekt am Ende dieser Sammlung hinzu. |
| [Clear](../../aspose.words.settings/odsofieldmapdatacollection/clear/)() | Entfernt alle Elemente aus dieser Sammlung. |
| [GetEnumerator](../../aspose.words.settings/odsofieldmapdatacollection/getenumerator/)() | Gibt ein Aufzählungsobjekt zurück, das verwendet werden kann, um alle Elemente in der Sammlung zu durchlaufen. |
| [RemoveAt](../../aspose.words.settings/odsofieldmapdatacollection/removeat/)(int) | Entfernt das Element am angegebenen Index. |

### Beispiele

Zeigt, wie auf die Sammlung von Daten zugegriffen wird, die Datenquellenspalten Briefvorlagenfeldern zuordnet.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// Diese Sammlung definiert, wie ein Seriendruck Spalten aus einer Datenquelle zuordnet
// zu vordefinierten MERGEFIELD-, ADRESSBLOCK- und GREETINGLINE-Feldern.
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

// Die Elemente in dieser Sammlung klonen.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Verwenden Sie die "RemoveAt"-Methodenelemente einzeln nach Index.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// Verwenden Sie die "Clear"-Methode, um die gesamte Sammlung auf einmal zu löschen.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Siehe auch

* class [OdsoFieldMapData](../odsofieldmapdata/)
* property [FieldMapDatas](../odso/fieldmapdatas/)
* namensraum [Aspose.Words.Settings](../../aspose.words.settings/)
* Montage [Aspose.Words](../../)


