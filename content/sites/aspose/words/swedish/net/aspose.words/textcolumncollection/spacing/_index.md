---
title: TextColumnCollection.Spacing
second_title: Aspose.Words för .NET API Referens
description: TextColumnCollection fast egendom. När kolumner är jämnt fördelade hämtas eller ställer in mängden utrymme mellan varje kolumn i poäng.
type: docs
weight: 50
url: /sv/net/aspose.words/textcolumncollection/spacing/
---
## TextColumnCollection.Spacing property

När kolumner är jämnt fördelade, hämtas eller ställer in mängden utrymme mellan varje kolumn i poäng.

```csharp
public double Spacing { get; set; }
```

### Anmärkningar

Har effekt endast när[`EvenlySpaced`](../evenlyspaced/) är satt till **Sann** .

### Exempel

Visar hur man skapar flera jämnt fördelade kolumner i ett avsnitt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### Se även

* class [TextColumnCollection](../)
* namnutrymme [Aspose.Words](../../textcolumncollection/)
* hopsättning [Aspose.Words](../../../)


