---
title: Table.ClearShading
second_title: Aspose.Words för .NET API Referens
description: Table metod. Tar bort all skuggning på bordet.
type: docs
weight: 380
url: /sv/net/aspose.words.tables/table/clearshading/
---
## Table.ClearShading method

Tar bort all skuggning på bordet.

```csharp
public void ClearShading()
```

### Exempel

Visar hur man tillämpar en konturram på en tabell.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Rikta in tabellen mot mitten av sidan.
table.Alignment = TableAlignment.Center;

// Rensa alla befintliga kanter och skuggningar från tabellen.
table.ClearBorders();
table.ClearShading();

// Lägg till gröna kanter till tabellens konturer.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// Fyll cellerna med en ljusgrön solid färg.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

### Se även

* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


