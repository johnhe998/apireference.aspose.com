---
title: FieldNextIf.RightExpression
second_title: Aspose.Words för .NET API Referens
description: FieldNextIf fast egendom. Hämtar eller ställer in den högra delen av jämförelseuttrycket.
type: docs
weight: 40
url: /sv/net/aspose.words.fields/fieldnextif/rightexpression/
---
## FieldNextIf.RightExpression property

Hämtar eller ställer in den högra delen av jämförelseuttrycket.

```csharp
public string RightExpression { get; set; }
```

### Exempel

Visar hur du använder NEXT/NEXTIF-fält för att slå samman flera rader till en sida under en e-postkoppling.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Skapa en datakälla för vår brevkoppling med 3 rader.
    // En sammanslagning som använder den här tabellen skulle normalt skapa ett 3-sidigt dokument.
    DataTable table = new DataTable("Employees");
    table.Columns.Add("Courtesy Title");
    table.Columns.Add("First Name");
    table.Columns.Add("Last Name");
    table.Rows.Add("Mr.", "John", "Doe");
    table.Rows.Add("Mrs.", "Jane", "Cardholder");
    table.Rows.Add("Mr.", "Joe", "Bloggs");

    InsertMergeFields(builder, "First row: ");

    // Om vi har flera sammanslagningsfält med samma fältnamn,
    // de kommer att ta emot data från samma rad i datakällan och visa samma värde efter sammanslagningen.
    // Ett NÄSTA fält talar om för brevkopplingen omedelbart att flytta ned en rad,
    // vilket betyder att alla MERGEFIELDs som följer fältet NÄSTA kommer att ta emot data från nästa rad.
    // Se till att aldrig försöka hoppa till nästa rad medan du redan är på den sista raden.
    FieldNext fieldNext = (FieldNext)builder.InsertField(FieldType.FieldNext, true);

    Assert.AreEqual(" NEXT ", fieldNext.GetFieldCode());

    // Efter sammanslagning, datakällans värden som dessa MERGEFIELDs accepterar
     // kommer att hamna på samma sida som MERGEFIELDs ovan.
    InsertMergeFields(builder, "Second row: ");

    // Ett NEXTIF-fält har samma funktion som ett NEXT-fält,
    // men den hoppar till nästa rad endast om ett påstående som konstruerats av följande 3 egenskaper är sant.
    FieldNextIf fieldNextIf = (FieldNextIf)builder.InsertField(FieldType.FieldNextIf, true);
    fieldNextIf.LeftExpression = "5";
    fieldNextIf.RightExpression = "2 + 3";
    fieldNextIf.ComparisonOperator = "=";

    Assert.AreEqual(" NEXTIF  5 = \"2 + 3\"", fieldNextIf.GetFieldCode());

    // Om jämförelsen i fältet ovan är korrekt,
    // följande 3 sammanslagningsfält tar data från den tredje raden.
    // Annars kommer dessa fält att ta data från rad 2 igen.
    InsertMergeFields(builder, "Third row: ");

    doc.MailMerge.Execute(table);

      // Vår datakälla har 3 rader, och vi hoppade över rader två gånger.
    // Vårt utdatadokument kommer att ha 1 sida med data från alla tre raderna.
    doc.Save(ArtifactsDir + "Field.NEXT.NEXTIF.docx");

/// <summary>
/// Använder en dokumentbyggare för att infoga MERGEFIELDs för en datakälla som innehåller kolumner med namnet "Courtesy Title", "First Name" och "Last Name".
/// </summary>
public void InsertMergeFields(DocumentBuilder builder, string firstFieldTextBefore)
{
    InsertMergeField(builder, "Courtesy Title", firstFieldTextBefore, " ");
    InsertMergeField(builder, "First Name", null, " ");
    InsertMergeField(builder, "Last Name", null, null);
    builder.InsertParagraph();
}

/// <summary>
/// Använder en dokumentbyggare för att infoga ett MERRGEFIELD med specificerade egenskaper.
/// </summary>
public void InsertMergeField(DocumentBuilder builder, string fieldName, string textBefore, string textAfter)
{
    FieldMergeField field = (FieldMergeField) builder.InsertField(FieldType.FieldMergeField, true);
    field.FieldName = fieldName;
    field.TextBefore = textBefore;
    field.TextAfter = textAfter;
}
```

### Se även

* class [FieldNextIf](../)
* namnutrymme [Aspose.Words.Fields](../../fieldnextif/)
* hopsättning [Aspose.Words](../../../)


