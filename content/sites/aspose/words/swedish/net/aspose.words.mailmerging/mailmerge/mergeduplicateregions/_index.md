---
title: MailMerge.MergeDuplicateRegions
second_title: Aspose.Words för .NET API Referens
description: MailMerge fast egendom. Hämtar eller ställer in ett värde som indikerar om alla dokumentkopplingsregioner med namnet på en datakälla ska slås samman under körning av en epostkoppling med regioner mot datakällan eller bara den första.
type: docs
weight: 60
url: /sv/net/aspose.words.mailmerging/mailmerge/mergeduplicateregions/
---
## MailMerge.MergeDuplicateRegions property

Hämtar eller ställer in ett värde som indikerar om alla dokumentkopplingsregioner med namnet på en datakälla ska slås samman under körning av en e-postkoppling med regioner mot datakällan eller bara den första.

```csharp
public bool MergeDuplicateRegions { get; set; }
```

### Anmärkningar

Standardvärdet är **falsk** .

### Exempel

Visar hur man arbetar med dubbletter av kopplingsregioner.

```csharp
public void MergeDuplicateRegions(bool mergeDuplicateRegions)
{
    Document doc = CreateSourceDocMergeDuplicateRegions();
    DataTable dataTable = CreateSourceTableMergeDuplicateRegions();

    // Om vi ställer in egenskapen "MergeDuplicateRegions" till "false", kommer kopplingen att påverka den första regionen,
    // medan MERGEFIELDs i den andra kommer att lämnas i pre-merge-tillståndet.
    // För att få båda regionerna sammanslagna så,
    // vi skulle behöva köra sammanslagningen två gånger på en tabell med samma namn.
    // Om vi ställer in egenskapen "MergeDuplicateRegions" till "true", kommer sammanslagningen att påverka båda regionerna.
    doc.MailMerge.MergeDuplicateRegions = mergeDuplicateRegions;

    doc.MailMerge.ExecuteWithRegions(dataTable);
    doc.Save(ArtifactsDir + "MailMerge.MergeDuplicateRegions.docx");
}

/// <summary>
/// Returnerar ett dokument som innehåller två dubbletter av kopplingsregioner (som delar samma namn i "TableStart/End"-taggarna).
/// </summary>
private static Document CreateSourceDocMergeDuplicateRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column1");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");
    builder.InsertParagraph();

    builder.InsertField(" MERGEFIELD TableStart:MergeRegion");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion");

    return doc;
}

/// <summary>
/// Skapar en datatabell med en rad och två kolumner.
/// </summary>
private static DataTable CreateSourceTableMergeDuplicateRegions()
{
    DataTable dataTable = new DataTable("MergeRegion");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value 1", "Value 2" });

    return dataTable;
}
```

### Se även

* class [MailMerge](../)
* namnutrymme [Aspose.Words.MailMerging](../../mailmerge/)
* hopsättning [Aspose.Words](../../../)


