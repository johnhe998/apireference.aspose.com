---
title: RowFormat.HeadingFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: RowFormat propriété. Vrai si la ligne est répétée en tant quentête de tableau sur chaque page lorsque le tableau sétend sur plusieurs pages.
type: docs
weight: 30
url: /fr/net/aspose.words.tables/rowformat/headingformat/
---
## RowFormat.HeadingFormat property

Vrai si la ligne est répétée en tant qu'en-tête de tableau sur chaque page lorsque le tableau s'étend sur plusieurs pages.

```csharp
public bool HeadingFormat { get; set; }
```

### Exemples

Montre comment créer un tableau avec des lignes qui se répètent sur chaque page.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();

// Toutes les lignes insérées alors que le drapeau "HeadingFormat" est défini sur "true"
// apparaîtra en haut du tableau sur chaque page qu'il couvre.
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Write("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Write("Heading row 2");
builder.EndRow();

builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
builder.RowFormat.HeadingFormat = false;

// Ajoutez suffisamment de lignes pour que le tableau s'étende sur deux pages.
for (int i = 0; i < 50; i++)
{
    builder.InsertCell();
    builder.Write($"Row {table.Rows.Count}, column 1.");
    builder.InsertCell();
    builder.Write($"Row {table.Rows.Count}, column 2.");
    builder.EndRow();
}

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableSetHeadingRow.docx");
```

### Voir également

* class [RowFormat](../)
* espace de noms [Aspose.Words.Tables](../../rowformat/)
* Assemblée [Aspose.Words](../../../)


