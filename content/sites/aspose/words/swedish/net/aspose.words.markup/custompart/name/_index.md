---
title: CustomPart.Name
second_title: Aspose.Words för .NET API Referens
description: CustomPart fast egendom. Hämtar eller ställer in denna dels absoluta namn i OOXMLpaketet eller målURL.
type: docs
weight: 50
url: /sv/net/aspose.words.markup/custompart/name/
---
## CustomPart.Name property

Hämtar eller ställer in denna dels absoluta namn i OOXML-paketet eller mål-URL.

```csharp
public string Name { get; set; }
```

### Anmärkningar

Om relationsmålet är internt är den här egenskapen det absoluta delnamnet i paketet. Om relationsmålet är externt är den här egenskapen mål-URL.

Standardvärdet är en tom sträng. Ett giltigt värde måste vara en icke-tom sträng.

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

* class [CustomPart](../)
* namnutrymme [Aspose.Words.Markup](../../custompart/)
* hopsättning [Aspose.Words](../../../)


