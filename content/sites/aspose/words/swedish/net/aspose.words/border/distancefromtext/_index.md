---
title: Border.DistanceFromText
second_title: Aspose.Words för .NET API Referens
description: Border fast egendom. Hämtar eller ställer in avståndet mellan kanten från text eller från sidkanten i punkter.
type: docs
weight: 20
url: /sv/net/aspose.words/border/distancefromtext/
---
## Border.DistanceFromText property

Hämtar eller ställer in avståndet mellan kanten från text eller från sidkanten i punkter.

```csharp
public double DistanceFromText { get; set; }
```

### Anmärkningar

Har ingen effekt och kommer automatiskt att nollställas för tabellcellers gränser.

### Exempel

Visar hur man skapar en bred blå bandkant längst upp på första sidan.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

### Se även

* class [Border](../)
* namnutrymme [Aspose.Words](../../border/)
* hopsättning [Aspose.Words](../../../)


