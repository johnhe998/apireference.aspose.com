---
title: FindReplaceOptions.LegacyMode
second_title: Aspose.Words för .NET API Referens
description: FindReplaceOptions fast egendom. Hämtar eller ställer in ett booleskt värde som indikerar att gammal hitta/ersätt algoritm används.
type: docs
weight: 110
url: /sv/net/aspose.words.replacing/findreplaceoptions/legacymode/
---
## FindReplaceOptions.LegacyMode property

Hämtar eller ställer in ett booleskt värde som indikerar att gammal hitta/ersätt algoritm används.

```csharp
public bool LegacyMode { get; set; }
```

### Anmärkningar

Använd denna flagga om du behöver exakt samma beteende som innan den avancerade sök-/ersättfunktionen introducerades. Observera att den gamla algoritmen inte stöder avancerade funktioner som att ersätta med pauser, tillämpa formatering och så vidare.

### Exempel

Visar hur man känner igen och använder ersättningar inom ersättningsmönster.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Jason gave money to Paul.");

Regex regex = new Regex(@"([A-z]+) gave money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions();
options.UseSubstitutions = true;

// Att använda äldre läge stöder inte många avancerade funktioner, så vi måste ställa in det på "false".
options.LegacyMode = false;

doc.Range.Replace(regex, @"$2 took money from $1", options);

Assert.AreEqual(doc.GetText(), "Paul took money from Jason.\f");
```

### Se även

* class [FindReplaceOptions](../)
* namnutrymme [Aspose.Words.Replacing](../../findreplaceoptions/)
* hopsättning [Aspose.Words](../../../)


