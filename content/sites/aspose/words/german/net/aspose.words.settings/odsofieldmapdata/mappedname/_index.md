---
title: OdsoFieldMapData.MappedName
second_title: Aspose.Words für .NET-API-Referenz
description: OdsoFieldMapData eigendom. Gibt den vordefinierten Briefvorlagenfeldnamen an der der Spaltennummer zugeordnet werden soll die durch angegeben wirdColumn Eigenschaft innerhalb dieser Feldzuordnung. Der Standardwert ist eine leere Zeichenfolge.
type: docs
weight: 30
url: /de/net/aspose.words.settings/odsofieldmapdata/mappedname/
---
## OdsoFieldMapData.MappedName property

Gibt den vordefinierten Briefvorlagenfeldnamen an, der der Spaltennummer zugeordnet werden soll, die durch angegeben wird[`Column`](../column/) Eigenschaft innerhalb dieser Feldzuordnung. Der Standardwert ist eine leere Zeichenfolge.

```csharp
public string MappedName { get; set; }
```

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

* class [OdsoFieldMapData](../)
* namensraum [Aspose.Words.Settings](../../odsofieldmapdata/)
* Montage [Aspose.Words](../../../)


