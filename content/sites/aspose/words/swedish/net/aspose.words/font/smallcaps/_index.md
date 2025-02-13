---
title: Font.SmallCaps
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Sant om teckensnittet är formaterat som små versaler.
type: docs
weight: 360
url: /sv/net/aspose.words/font/smallcaps/
---
## Font.SmallCaps property

Sant om teckensnittet är formaterat som små versaler.

```csharp
public bool SmallCaps { get; set; }
```

### Exempel

Visar hur man formaterar en körning för att visa dess innehåll med versaler.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// Det finns två sätt att få en körning att visa sin gemena text med versaler utan att ändra innehållet.
// 1 - Ställ in AllCaps-flaggan för att visa alla tecken med vanliga versaler:
Run run = new Run(doc, "all capitals");
run.Font.AllCaps = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

// 2 - Ställ in SmallCaps-flaggan för att visa alla tecken med små versaler:
// Om ett tecken är gemener kommer det att visas med versaler
// men kommer att ha samma höjd som gemener (teckensnittets x-höjd).
// Tecken som ursprungligen stod i versaler kommer att se likadana ut.
run = new Run(doc, "Small Capitals");
run.Font.SmallCaps = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.Caps.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


