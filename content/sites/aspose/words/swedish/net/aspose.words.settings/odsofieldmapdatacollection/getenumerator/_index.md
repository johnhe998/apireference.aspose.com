---
title: OdsoFieldMapDataCollection.GetEnumerator
second_title: Aspose.Words för .NET API Referens
description: OdsoFieldMapDataCollection metod. Returnerar ett uppräkningsobjekt som kan användas för att iterera över alla objekt i samlingen.
type: docs
weight: 60
url: /sv/net/aspose.words.settings/odsofieldmapdatacollection/getenumerator/
---
## OdsoFieldMapDataCollection.GetEnumerator method

Returnerar ett uppräkningsobjekt som kan användas för att iterera över alla objekt i samlingen.

```csharp
public IEnumerator<OdsoFieldMapData> GetEnumerator()
```

### Exempel

Visar hur du får åtkomst till insamlingen av data som mappar datakällans kolumner för att slå samman fält.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// Den här samlingen definierar hur en sammanslagning kommer att mappa kolumner från en datakälla
// till fördefinierade fält MERGEFIELD, ADDRESSBLOCK och GREETINGLINE.
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

// Klona elementen i den här samlingen.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Använd "RemoveAt"-metodens element individuellt efter index.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// Använd "Rensa"-metoden för att rensa hela samlingen på en gång.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Se även

* class [OdsoFieldMapData](../../odsofieldmapdata/)
* class [OdsoFieldMapDataCollection](../)
* namnutrymme [Aspose.Words.Settings](../../odsofieldmapdatacollection/)
* hopsättning [Aspose.Words](../../../)


