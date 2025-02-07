---
title: MailMerge.UseWholeParagraphAsRegion
second_title: Aspose.Words för .NET API Referens
description: MailMerge fast egendom. Hämtar eller ställer in ett värde som anger om hela stycket med TableStart eller TableEnd field eller särskilt intervall mellan TableStart och TableEndfält ska inkluderas i kopplingsområdet.
type: docs
weight: 160
url: /sv/net/aspose.words.mailmerging/mailmerge/usewholeparagraphasregion/
---
## MailMerge.UseWholeParagraphAsRegion property

Hämtar eller ställer in ett värde som anger om hela stycket med TableStart eller TableEnd field eller särskilt intervall mellan TableStart och TableEnd-fält ska inkluderas i kopplingsområdet.

```csharp
public bool UseWholeParagraphAsRegion { get; set; }
```

### Anmärkningar

Standardvärdet är **Sann** .

### Exempel

Visar förhållandet mellan kopplingsregioner och stycken.

```csharp
public void UseWholeParagraphAsRegion(bool useWholeParagraphAsRegion)
{
    Document doc = CreateSourceDocWithNestedMergeRegions();
    DataTable dataTable = CreateSourceTableDataTableForOneRegion();

    // Som standard kan ett stycke inte tillhöra mer än en kopplingsregion.
    // Innehållet i vårt dokument uppfyller inte dessa kriterier.
    // Om vi ställer in flaggan "UseWholeParagraphAsRegion" till "true",
    // att köra en sammanslagning av det här dokumentet ger ett undantag.
    // Om vi ställer in flaggan "UseWholeParagraphAsRegion" till "false",
    // vi kommer att kunna köra en sammanfogning av detta dokument.
    doc.MailMerge.UseWholeParagraphAsRegion = useWholeParagraphAsRegion;

    if (useWholeParagraphAsRegion)
        Assert.Throws<InvalidOperationException>(() => doc.MailMerge.ExecuteWithRegions(dataTable));
    else
        doc.MailMerge.ExecuteWithRegions(dataTable);

    // Brevkopplingen fyller vår första region medan den andra regionen lämnas oanvänd
    // eftersom det är regionen som bryter mot regeln.
    doc.Save(ArtifactsDir + "MailMerge.UseWholeParagraphAsRegion.docx");
}

/// <summary>
/// Skapa ett dokument med två kopplingsregioner som delar ett stycke.
/// </summary>
private static Document CreateSourceDocWithNestedMergeRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Write("Region 1: ");
    builder.InsertField(" MERGEFIELD TableStart:MyTable");
    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MyTable");

    builder.Write(", Region 2: ");
    builder.InsertField(" MERGEFIELD TableStart:MyOtherTable");
    builder.InsertField(" MERGEFIELD TableEnd:MyOtherTable");

    return doc;
}

/// <summary>
/// Skapa en datatabell som kan fylla en region under en sammanfogning.
/// </summary>
private static DataTable CreateSourceTableDataTableForOneRegion()
{
    DataTable dataTable = new DataTable("MyTable");
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


