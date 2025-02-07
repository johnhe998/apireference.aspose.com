---
title: BorderCollection.DistanceFromText
second_title: Aspose.Words för .NET API Referens
description: BorderCollection fast egendom. Hämtar eller ställer in avståndet mellan gränsen från text i punkter.
type: docs
weight: 40
url: /sv/net/aspose.words/bordercollection/distancefromtext/
---
## BorderCollection.DistanceFromText property

Hämtar eller ställer in avståndet mellan gränsen från text i punkter.

```csharp
public double DistanceFromText { get; set; }
```

### Anmärkningar

Hämtar avståndet från text för den första kanten.

Ställer in avståndet från text för alla kanter i samlingen exklusive diagonala kanter.

Har ingen effekt och kommer automatiskt att nollställas för tabellcellers kantlinjer.

### Exempel

Visar hur man skapar grön vågig sidkant med en skugga.

```csharp
Document doc = new Document();
PageSetup pageSetup = doc.Sections[0].PageSetup;

pageSetup.Borders.LineStyle = LineStyle.DoubleWave;
pageSetup.Borders.LineWidth = 2;
pageSetup.Borders.Color = Color.Green;
pageSetup.Borders.DistanceFromText = 24;
pageSetup.Borders.Shadow = true;

doc.Save(ArtifactsDir + "PageSetup.PageBorders.docx");
```

### Se även

* class [BorderCollection](../)
* namnutrymme [Aspose.Words](../../bordercollection/)
* hopsättning [Aspose.Words](../../../)


