---
title: Class CustomPartCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Markup.CustomPartCollection klass. Representerar en samling avCustomPart objekt.
type: docs
weight: 3670
url: /sv/net/aspose.words.markup/custompartcollection/
---
## CustomPartCollection class

Representerar en samling av[`CustomPart`](../custompart/) objekt.

```csharp
public class CustomPartCollection : IEnumerable<CustomPart>
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [CustomPartCollection](custompartcollection/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words.markup/custompartcollection/count/) { get; } | Hämtar antalet element som finns i samlingen. |
| [Item](../../aspose.words.markup/custompartcollection/item/) { get; set; } | Hämtar eller ställer in ett objekt på angivet index. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Add](../../aspose.words.markup/custompartcollection/add/)(CustomPart) | Lägger till ett föremål i samlingen. |
| [Clear](../../aspose.words.markup/custompartcollection/clear/)() | Tar bort alla element från samlingen. |
| [Clone](../../aspose.words.markup/custompartcollection/clone/)() | Gör en djup kopia av den här samlingen och dess föremål. |
| [GetEnumerator](../../aspose.words.markup/custompartcollection/getenumerator/)() | Returnerar ett uppräkningsobjekt som kan användas för att iterera över alla objekt i samlingen. |
| [RemoveAt](../../aspose.words.markup/custompartcollection/removeat/)(int) | Tar bort ett objekt vid angivet index. |

### Anmärkningar

Du behöver normalt inte skapa instanser av den här klassen. Du kommer åt anpassade delar relaterade till OOXML-paketet via[`PackageCustomParts`](../../aspose.words/document/packagecustomparts/) fast egendom.

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

* class [CustomPart](../custompart/)
* namnutrymme [Aspose.Words.Markup](../../aspose.words.markup/)
* hopsättning [Aspose.Words](../../)


