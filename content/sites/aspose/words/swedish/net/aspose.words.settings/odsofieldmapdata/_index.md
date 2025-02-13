---
title: Class OdsoFieldMapData
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Settings.OdsoFieldMapData klass. Anger hur en kolumn i den externa datakällan ska mappas till de fördefinierade sammanslagningsfälten i dokumentet.
type: docs
weight: 5600
url: /sv/net/aspose.words.settings/odsofieldmapdata/
---
## OdsoFieldMapData class

Anger hur en kolumn i den externa datakällan ska mappas till de fördefinierade sammanslagningsfälten i dokumentet.

```csharp
public class OdsoFieldMapData
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [OdsoFieldMapData](odsofieldmapdata/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Column](../../aspose.words.settings/odsofieldmapdata/column/) { get; set; } | Anger det nollbaserade indexet för kolumnen inom en extern datakälla som ska mappas till det lokala namnet på ett specifikt MERGEFIELD-fält. Standardvärdet är 0. |
| [MappedName](../../aspose.words.settings/odsofieldmapdata/mappedname/) { get; set; } | Anger det fördefinierade sammanslagningsfältets namn som ska mappas till kolumnnumret som anges av[`Column`](./column/) egenskap inom denna fältmappning. Standardvärdet är en tom sträng. |
| [Name](../../aspose.words.settings/odsofieldmapdata/name/) { get; set; } | Anger kolumnnamnet inom en extern datakälla för kolumnen vars index anges av[`Column`](./column/) property. Standardvärdet är en tom sträng. |
| [Type](../../aspose.words.settings/odsofieldmapdata/type/) { get; set; } | Anger om ett givet kopplingsfält har mappats till en kolumn i den givna externa datakällan eller inte. Standardvärdet ärDefault . |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Clone](../../aspose.words.settings/odsofieldmapdata/clone/)() | Returnerar en djup klon av detta objekt. |

### Anmärkningar

Microsoft Word tillhandahåller några fördefinierade sammanslagningsfältnamn som det tillåter att infoga i ett dokument som MERGEFIELD eller använder i fälten ADDRESSBLOCK eller GREETINGLINE. Den information som anges i`OdsoFieldMapData` gör det möjligt att mappa en kolumn i den externa datakällan till ett enda fördefinierat sammanslagningsfält.

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

* namnutrymme [Aspose.Words.Settings](../../aspose.words.settings/)
* hopsättning [Aspose.Words](../../)


