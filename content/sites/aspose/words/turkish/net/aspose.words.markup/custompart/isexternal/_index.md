---
title: CustomPart.IsExternal
second_title: Aspose.Words for .NET API Referansı
description: CustomPart mülk. Yanlış bu özel parça OOXML paketinin içinde saklanıyorsa.Doğru bu özel parça harici bir hedefse.
type: docs
weight: 40
url: /tr/net/aspose.words.markup/custompart/isexternal/
---
## CustomPart.IsExternal property

`Yanlış` bu özel parça OOXML paketinin içinde saklanıyorsa.`Doğru` bu özel parça harici bir hedefse.

```csharp
public bool IsExternal { get; set; }
```

### Notlar

Varsayılan değer`yanlış`.

### Örnekler

Bir belgenin isteğe bağlı özel parça koleksiyonuna nasıl erişileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// İkinci bölümü klonlayın, ardından klonu koleksiyona ekleyin.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// Koleksiyon üzerinde numaralandırın ve her parçayı yazdırın.
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

// Bu koleksiyondaki öğeleri tek tek veya bir kerede kaldırabiliriz.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### Ayrıca bakınız

* class [CustomPart](../)
* ad alanı [Aspose.Words.Markup](../../custompart/)
* toplantı [Aspose.Words](../../../)


