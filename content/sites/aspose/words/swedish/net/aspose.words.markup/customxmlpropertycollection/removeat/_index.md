---
title: CustomXmlPropertyCollection.RemoveAt
second_title: Aspose.Words för .NET API Referens
description: CustomXmlPropertyCollection metod. Tar bort en egenskap vid det angivna indexet.
type: docs
weight: 90
url: /sv/net/aspose.words.markup/customxmlpropertycollection/removeat/
---
## CustomXmlPropertyCollection.RemoveAt method

Tar bort en egenskap vid det angivna indexet.

```csharp
public void RemoveAt(int index)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| index | Int32 | Det nollbaserade indexet. |

### Exempel

Visar hur man arbetar med smarta taggars egenskaper för att få djupgående information om smarta taggar.

```csharp
Document doc = new Document(MyDir + "Smart tags.doc");

// En smart tagg visas i ett dokument med Microsoft Word känner igen en del av sin text som någon form av data,
// som ett namn, datum eller adress, och konverterar det till en hyperlänk som visar en lila prickad underlinje.
// I Word 2003 kan vi aktivera smarta taggar via "Verktyg" -> "Autokorrigeringsalternativ..." -> "SmartTags".
// I vårt indatadokument finns det tre objekt som Microsoft Word registrerade som smarta taggar.
// Smarta taggar kan vara kapslade, så den här samlingen innehåller fler.
SmartTag[] smartTags = doc.GetChildNodes(NodeType.SmartTag, true).OfType<SmartTag>().ToArray();

Assert.AreEqual(8, smartTags.Length);

// "Properties"-medlemmen i en smart tagg innehåller dess metadata, som kommer att vara olika för varje typ av smart tagg.
// Egenskaperna för en smart tagg av "datum"-typ innehåller dess år, månad och dag.
CustomXmlPropertyCollection properties = smartTags[7].Properties;

Assert.AreEqual(4, properties.Count);

using (IEnumerator<CustomXmlProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Property name: {enumerator.Current.Name}, value: {enumerator.Current.Value}");
        Assert.AreEqual("", enumerator.Current.Uri);
    }
}

// Vi kan också komma åt egenskaperna på olika sätt, till exempel ett nyckel-värdepar.
Assert.True(properties.Contains("Day"));
Assert.AreEqual("22", properties["Day"].Value);
Assert.AreEqual("2003", properties[2].Value);
Assert.AreEqual(1, properties.IndexOfKey("Month"));

// Nedan finns tre sätt att ta bort element från egenskapssamlingen.
// 1 - Ta bort efter index:
properties.RemoveAt(3);

Assert.AreEqual(3, properties.Count);

// 2 - Ta bort efter namn:
properties.Remove("Year");

Assert.AreEqual(2, properties.Count);

// 3 - Rensa hela samlingen på en gång:
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Se även

* class [CustomXmlPropertyCollection](../)
* namnutrymme [Aspose.Words.Markup](../../customxmlpropertycollection/)
* hopsättning [Aspose.Words](../../../)


