---
title: CustomPart.Clone
second_title: Aspose.Words für .NET-API-Referenz
description: CustomPart methode. Erstellt eine ausreichend tiefe Kopie des Objekts. Dupliziert die Bytes der nichtData wert.
type: docs
weight: 70
url: /de/net/aspose.words.markup/custompart/clone/
---
## CustomPart.Clone method

Erstellt eine ausreichend tiefe Kopie des Objekts. Dupliziert die Bytes der nicht[`Data`](../data/) wert.

```csharp
public CustomPart Clone()
```

### Beispiele

Zeigt, wie auf die Sammlung beliebiger benutzerdefinierter Teile eines Dokuments zugegriffen wird.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// Den zweiten Teil klonen, dann den Klon zur Sammlung hinzufügen.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// Aufzählen über die Sammlung und jeden Teil drucken.
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

// Wir können Elemente aus dieser Sammlung einzeln oder alle auf einmal entfernen.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### Siehe auch

* class [CustomPart](../)
* namensraum [Aspose.Words.Markup](../../custompart/)
* Montage [Aspose.Words](../../../)


