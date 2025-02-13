---
title: Table.SetShading
second_title: Aspose.Words för .NET API Referens
description: Table metod. Ställer in skuggning till de angivna värdena på hela tabellen.
type: docs
weight: 430
url: /sv/net/aspose.words.tables/table/setshading/
---
## Table.SetShading method

Ställer in skuggning till de angivna värdena på hela tabellen.

```csharp
public void SetShading(TextureIndex texture, Color foregroundColor, Color backgroundColor)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| texture | TextureIndex | Konsistensen att applicera. |
| foregroundColor | Color | Färgen på texturen. |
| backgroundColor | Color | Färgen på bakgrundsfyllningen. |

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

* enum [TextureIndex](../../../aspose.words/textureindex/)
* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


