---
title: FindReplaceOptions.MatchCase
second_title: Aspose.Words för .NET API Referens
description: FindReplaceOptions fast egendom. True indikerar skiftlägeskänslig jämförelse false indikerar skiftlägesokänslig jämförelse.
type: docs
weight: 120
url: /sv/net/aspose.words.replacing/findreplaceoptions/matchcase/
---
## FindReplaceOptions.MatchCase property

True indikerar skiftlägeskänslig jämförelse, false indikerar skiftlägesokänslig jämförelse.

```csharp
public bool MatchCase { get; set; }
```

### Exempel

Visar hur du växlar skiftlägeskänslighet när du utför en sök-och-ersätt-åtgärd.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Ruby bought a ruby necklace.");

// Vi kan använda ett "FindReplaceOptions"-objekt för att ändra sök-och-ersätt-processen.
FindReplaceOptions options = new FindReplaceOptions();

// Ställ in "MatchCase"-flaggan till "true" för att tillämpa skiftlägeskänslighet samtidigt som du hittar strängar att ersätta.
// Ställ in "MatchCase"-flaggan till "false" för att ignorera skiftläge när du söker efter text som ska ersättas.
options.MatchCase = matchCase;

doc.Range.Replace("Ruby", "Jade", options);

Assert.AreEqual(matchCase ? "Jade bought a ruby necklace." : "Jade bought a Jade necklace.",
    doc.GetText().Trim());
```

### Se även

* class [FindReplaceOptions](../)
* namnutrymme [Aspose.Words.Replacing](../../findreplaceoptions/)
* hopsättning [Aspose.Words](../../../)


