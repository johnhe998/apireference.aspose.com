---
title: Class CustomPart
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Markup.CustomPart klass. Representerar en anpassad godtyckligt innehåll del som inte definieras av ISO/IEC 29500standarden.
type: docs
weight: 3660
url: /sv/net/aspose.words.markup/custompart/
---
## CustomPart class

Representerar en anpassad (godtyckligt innehåll) del, som inte definieras av ISO/IEC 29500-standarden.

```csharp
public class CustomPart
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [CustomPart](custompart/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [ContentType](../../aspose.words.markup/custompart/contenttype/) { get; set; } | Anger innehållstypen för den här anpassade delen. |
| [Data](../../aspose.words.markup/custompart/data/) { get; set; } | Innehåller data för denna anpassade del. |
| [IsExternal](../../aspose.words.markup/custompart/isexternal/) { get; set; } | `Falsk` om denna anpassade del lagras i OOXML-paketet.`Sann` om den här anpassade delen är ett externt mål. |
| [Name](../../aspose.words.markup/custompart/name/) { get; set; } | Hämtar eller ställer in denna dels absoluta namn i OOXML-paketet eller mål-URL. |
| [RelationshipType](../../aspose.words.markup/custompart/relationshiptype/) { get; set; } | Hämtar eller ställer in relationstypen från den överordnade delen till den här anpassade delen. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Clone](../../aspose.words.markup/custompart/clone/)() | Gör en "tillräckligt djup" kopia av objektet. Duplicerar inte byten för[`Data`](./data/) värde. |

### Anmärkningar

Den här klassen representerar en OOXML-del som är ett mål för en "okänd relation". Alla relationer som inte definieras inom ISO/IEC 29500 anses vara "okända relationer". Okända relationer är tillåtna i ett Office Open XML-dokument förutsatt att de överensstämmer med till riktlinjer för uppmärkning av relationer.

Microsoft Word bevarar anpassade delar under öppna/spara-cykler. Lite ytterligare information kan hittas här http://blogs.msdn.com/dmahugh/archive/2006/11/25/arbitrary-content-in-an-opc-package.aspx

Aspose.Words gör även anpassade delar tur och retur och tillåter dessutom att programmässigt komma åt sådana delar via`CustomPart` och[`CustomPartCollection`](../custompartcollection/) objekt.

Blanda inte ihop anpassade delar med anpassade XML-data. Använda sig av[`CustomXmlPart`](../customxmlpart/) om du behöver för att komma åt anpassade XML-data.

### Exempel

Visar hur man kommer åt ett dokuments godtyckliga anpassade delarsamling.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// Klona den andra delen och lägg sedan till klonen i samlingen.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// Räkna upp samlingen och skriv ut varje del.
using (IEnumerator<CustomPart> enumerator = doc.PackageCustomParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Part index {index}:");
        Console.WriteLine($"\tName:\t\t\t\t{enumerator.Current.Name}");
        Console.WriteLine($"\tContent type:\t\t{enumerator.Current.ContentType}");
        Console.WriteLine($"\tRelationship type:\t{enumerator.Current.RelationshipType}");
        Console.WriteLine(enumerator.Current.IsExternal ?
            "\tSourced from outside the document" :
            $"\tStored within the document, length: {enumerator.Current.Data.Length} bytes");
        index++;
    }
}

// Vi kan ta bort element från denna samling individuellt eller alla på en gång.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### Se även

* namnutrymme [Aspose.Words.Markup](../../aspose.words.markup/)
* hopsättning [Aspose.Words](../../)


