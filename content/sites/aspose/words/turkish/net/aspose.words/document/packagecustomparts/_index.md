---
title: Document.PackageCustomParts
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. Bilinmeyen ilişkiler kullanarak OOXML paketine bağlanan özel parçaların keyfi içerik koleksiyonunu alır veya ayarlar.
type: docs
weight: 290
url: /tr/net/aspose.words/document/packagecustomparts/
---
## Document.PackageCustomParts property

"Bilinmeyen ilişkiler" kullanarak OOXML paketine bağlanan özel parçaların (keyfi içerik) koleksiyonunu alır veya ayarlar.

```csharp
public CustomPartCollection PackageCustomParts { get; set; }
```

### Notlar

Bu özel parçaları Özel XML Verileri ile karıştırmayın. Özel XML bölümlerine erişmeniz gerekiyorsa, [`CustomXmlParts`](../customxmlparts/) Emlak.

Bu koleksiyon, ebeveyni OOXML paketi olan ve hedefleri "bilinmeyen bir ilişki" olan OOXML parçalarını içerir. Daha fazla bilgi için bkz.[`CustomPart`](../../../aspose.words.markup/custompart/).

Aspose.Words, özel parçaları yalnızca OOXML belgelerine yükler ve kaydeder.

Bu özellik olamaz`hükümsüz`.

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

* class [CustomPartCollection](../../../aspose.words.markup/custompartcollection/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


