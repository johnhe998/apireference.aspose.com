---
title: Border.ClearFormatting
second_title: Aspose.Words för .NET API Referens
description: Border metod. Återställer gränsegenskaper till standardvärden.
type: docs
weight: 70
url: /sv/net/aspose.words/border/clearformatting/
---
## Border.ClearFormatting method

Återställer gränsegenskaper till standardvärden.

```csharp
public void ClearFormatting()
```

### Anmärkningar

När gränsegenskaper återställs till standardvärden är gränsen osynlig.

### Exempel

Visar hur man tar bort kanter från ett stycke.

```csharp
Document doc = new Document(MyDir + "Borders.docx");

// Varje stycke har en individuell uppsättning ramar.
// Vi kan komma åt inställningarna för utseendet på dessa gränser via objektet styckeformat.
BorderCollection borders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;

Assert.AreEqual(Color.Red.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(3.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.Single, borders[0].LineStyle);
Assert.True(borders[0].IsVisible);

// Vi kan ta bort en kantlinje på en gång genom att köra metoden ClearFormatting. 
// Att köra den här metoden på varje kant i ett stycke tar bort alla dess kanter.
foreach (Border border in borders)
    border.ClearFormatting();

Assert.AreEqual(Color.Empty.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(0.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.None, borders[0].LineStyle);
Assert.IsFalse(borders[0].IsVisible);

doc.Save(ArtifactsDir + "Border.ClearFormatting.docx");
```

### Se även

* class [Border](../)
* namnutrymme [Aspose.Words](../../border/)
* hopsättning [Aspose.Words](../../../)


