---
title: Enum OdsoFieldMappingType
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Settings.OdsoFieldMappingType uppräkning. Anger möjliga typer som används för att indikera om ett givet kopplingsfält har mappats till en kolumn i den givna externa datakällan.
type: docs
weight: 5620
url: /sv/net/aspose.words.settings/odsofieldmappingtype/
---
## OdsoFieldMappingType enumeration

Anger möjliga typer som används för att indikera om ett givet kopplingsfält har mappats till en kolumn i den givna externa datakällan.

```csharp
public enum OdsoFieldMappingType
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Column | `0` | Anger att kopplingsfältet har mappats till en kolumn i den givna externa datakällan. |
| Null | `1` | Anger att kopplingsfältet inte har mappats till en kolumn i den givna externa datakällan. |
| Default | `1` | MotsvararNull . |

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

* property [Type](../odsofieldmapdata/type/)
* namnutrymme [Aspose.Words.Settings](../../aspose.words.settings/)
* hopsättning [Aspose.Words](../../)


