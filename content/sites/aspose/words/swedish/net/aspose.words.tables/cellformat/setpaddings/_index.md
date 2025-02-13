---
title: CellFormat.SetPaddings
second_title: Aspose.Words för .NET API Referens
description: CellFormat metod. Ställer in mängden utrymme i poäng som ska läggas till till vänster/överst/höger/botten av innehållet i cellen.
type: docs
weight: 160
url: /sv/net/aspose.words.tables/cellformat/setpaddings/
---
## CellFormat.SetPaddings method

Ställer in mängden utrymme (i poäng) som ska läggas till till vänster/överst/höger/botten av innehållet i cellen.

```csharp
public void SetPaddings(double leftPadding, double topPadding, double rightPadding, 
    double bottomPadding)
```

### Exempel

Visar hur man fyller på innehållet i en cell med blanksteg.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ställ in ett utfyllnadsavstånd (i punkter) mellan gränsen och textinnehållet
// av varje tabellcell vi skapar med dokumentbyggaren. 
builder.CellFormat.SetPaddings(5, 10, 40, 50);

// Skapa en tabell med en cell vars innehåll kommer att ha blanksteg.
builder.StartTable();
builder.InsertCell();
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
              "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

doc.Save(ArtifactsDir + "CellFormat.Padding.docx");
```

### Se även

* class [CellFormat](../)
* namnutrymme [Aspose.Words.Tables](../../cellformat/)
* hopsättning [Aspose.Words](../../../)


