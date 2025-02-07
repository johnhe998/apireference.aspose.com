---
title: BuiltInDocumentProperties.HeadingPairs
second_title: Aspose.Words för .NET API Referens
description: BuiltInDocumentProperties fast egendom. Anger dokumentrubriker och deras namn.
type: docs
weight: 110
url: /sv/net/aspose.words.properties/builtindocumentproperties/headingpairs/
---
## BuiltInDocumentProperties.HeadingPairs property

Anger dokumentrubriker och deras namn.

```csharp
public object[] HeadingPairs { get; set; }
```

### Anmärkningar

Varje rubrikpar upptar två element i denna array.

Det första elementet i paret är aString och anger rubrikens namn. Det andra elementet i paret är enInt32 och specificerar antalet document delar för denna rubrik i[`TitlesOfParts`](../titlesofparts/) fast egendom.

Den totala summan av antal för alla rubrikpar i den här egenskapen måste vara lika med antalet element i[`TitlesOfParts`](../titlesofparts/) fast egendom.

Aspose.Words uppdaterar inte den här egenskapen.

### Exempel

Visar förhållandet mellan "HeadingPairs" och "TitlesOfParts" egenskaper.

```csharp
Document doc = new Document(MyDir + "Heading pairs and titles of parts.docx");

// Vi kan hitta de kombinerade värdena för dessa samlingar via
// "Fil" -> "Egenskaper" -> "Avancerade egenskaper" -> Fliken "Innehåll".
// Egenskapen HeadingPairs är en samling av <string, int> parar det
// bestämmer hur många dokumentdelar en rubrik sträcker sig över.
object[] headingPairs = doc.BuiltInDocumentProperties.HeadingPairs;

// Egenskapen TitlesOfParts innehåller namnen på delar som hör till ovanstående rubriker.
string[] titlesOfParts = doc.BuiltInDocumentProperties.TitlesOfParts;

int headingPairsIndex = 0;
int titlesOfPartsIndex = 0;
while (headingPairsIndex < headingPairs.Length)
{
    Console.WriteLine($"Parts for {headingPairs[headingPairsIndex++]}:");
    int partsCount = Convert.ToInt32(headingPairs[headingPairsIndex++]);

    for (int i = 0; i < partsCount; i++)
        Console.WriteLine($"\t\"{titlesOfParts[titlesOfPartsIndex++]}\"");
}
```

### Se även

* class [BuiltInDocumentProperties](../)
* namnutrymme [Aspose.Words.Properties](../../builtindocumentproperties/)
* hopsättning [Aspose.Words](../../../)


