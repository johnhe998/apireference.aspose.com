---
title: OdsoFieldMapData.Type
second_title: Aspose.Words for .NET API Referansı
description: OdsoFieldMapData mülk. Belirli bir adres mektup birleştirme alanının verilen harici veri kaynağındaki bir sütunla eşlenip eşlenmediğini belirtir. Varsayılan değerDefault .
type: docs
weight: 50
url: /tr/net/aspose.words.settings/odsofieldmapdata/type/
---
## OdsoFieldMapData.Type property

Belirli bir adres mektup birleştirme alanının, verilen harici veri kaynağındaki bir sütunla eşlenip eşlenmediğini belirtir. Varsayılan değerDefault .

```csharp
public OdsoFieldMappingType Type { get; set; }
```

### Örnekler

Alanları birleştirmek için veri kaynağı sütunlarını eşleyen veri koleksiyonuna nasıl erişileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// Bu koleksiyon, adres mektup birleştirmenin bir veri kaynağındaki sütunları nasıl eşleyeceğini tanımlar
// önceden tanımlanmış MERGEFIELD, ADRESSBLOCK ve GREETINGLINE alanlarına.
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

// Bu koleksiyondaki öğeleri klonlayın.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// "RemoveAt" yöntem öğelerini dizine göre ayrı ayrı kullanın.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// Tüm koleksiyonu bir kerede temizlemek için "Clear" yöntemini kullanın.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Ayrıca bakınız

* enum [OdsoFieldMappingType](../../odsofieldmappingtype/)
* class [OdsoFieldMapData](../)
* ad alanı [Aspose.Words.Settings](../../odsofieldmapdata/)
* toplantı [Aspose.Words](../../../)


