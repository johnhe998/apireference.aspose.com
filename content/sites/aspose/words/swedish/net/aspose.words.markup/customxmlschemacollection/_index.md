---
title: Class CustomXmlSchemaCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Markup.CustomXmlSchemaCollection klass. En samling strängar som representerar XMLscheman som är associerade med en anpassad XMLdel.
type: docs
weight: 3720
url: /sv/net/aspose.words.markup/customxmlschemacollection/
---
## CustomXmlSchemaCollection class

En samling strängar som representerar XML-scheman som är associerade med en anpassad XML-del.

```csharp
public class CustomXmlSchemaCollection : IEnumerable<string>
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words.markup/customxmlschemacollection/count/) { get; } | Hämtar antalet element som finns i samlingen. |
| [Item](../../aspose.words.markup/customxmlschemacollection/item/) { get; set; } | Hämtar eller ställer in elementet vid angivet index. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Add](../../aspose.words.markup/customxmlschemacollection/add/)(string) | Lägger till ett föremål i samlingen. |
| [Clear](../../aspose.words.markup/customxmlschemacollection/clear/)() | Tar bort alla element från samlingen. |
| [Clone](../../aspose.words.markup/customxmlschemacollection/clone/)() | Gör en djup klon av detta objekt. |
| [GetEnumerator](../../aspose.words.markup/customxmlschemacollection/getenumerator/)() | Returnerar ett uppräkningsobjekt som kan användas för att iterera över alla objekt i samlingen. |
| [IndexOf](../../aspose.words.markup/customxmlschemacollection/indexof/)(string) | Returnerar det nollbaserade indexet för det angivna värdet i samlingen. |
| [Remove](../../aspose.words.markup/customxmlschemacollection/remove/)(string) | Tar bort det angivna värdet från samlingen. |
| [RemoveAt](../../aspose.words.markup/customxmlschemacollection/removeat/)(int) | Tar bort ett värde vid det angivna indexet. |

### Anmärkningar

Du skapar inte instanser av den här klassen. Du kommer åt samlingen av XML-scheman för en anpassad XML part via[`Schemas`](../customxmlpart/schemas/) fast egendom.

### Exempel

Visar hur man arbetar med en XML-schemasamling.

```csharp
Document doc = new Document();

string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello, World!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

// Lägg till en XML-schemaassociation.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Klona den anpassade XML-delens XML-schemaassociationssamling,
// och lägg sedan till ett par nya scheman till klonen.
CustomXmlSchemaCollection schemas = xmlPart.Schemas.Clone();
schemas.Add("http://www.w3.org/2001/XMLSchema-instance");
schemas.Add("http://schemas.microsoft.com/office/2006/metadata/contentType");

Assert.AreEqual(3, schemas.Count);
Assert.AreEqual(2, schemas.IndexOf("http://schemas.microsoft.com/office/2006/metadata/contentType"));

// Räkna upp scheman och skriv ut varje element.
using (IEnumerator<string> enumerator = schemas.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine(enumerator.Current);
}

// Nedan finns tre sätt att ta bort scheman från samlingen.
// 1 - Ta bort ett schema efter index:
schemas.RemoveAt(2);

// 2 - Ta bort ett schema efter värde:
schemas.Remove("http://www.w3.org/2001/XMLSchema");

// 3 - Använd metoden "Rensa" för att tömma samlingen på en gång.
schemas.Clear();

Assert.AreEqual(0, schemas.Count);
```

### Se även

* namnutrymme [Aspose.Words.Markup](../../aspose.words.markup/)
* hopsättning [Aspose.Words](../../)


