---
title: Interface IFieldUserPromptRespondent
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Fields.IFieldUserPromptRespondent gränssnitt. Representerar respondenten för användarmeddelanden under fältuppdatering.
type: docs
weight: 2560
url: /sv/net/aspose.words.fields/ifielduserpromptrespondent/
---
## IFieldUserPromptRespondent interface

Representerar respondenten för användarmeddelanden under fältuppdatering.

```csharp
public interface IFieldUserPromptRespondent
```

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Respond](../../aspose.words.fields/ifielduserpromptrespondent/respond/)(string, string) | När den är implementerad returneras ett svar från användaren vid uppmaning. Din implementering bör returneras **null** för att indikera att användaren inte har svarat på prompten (dvs användaren har tryckt på knappen Avbryt i promptfönstret). |

### Anmärkningar

Fälten ASK och FILLIN är exempel på fält som ber användaren om något svar. Implementera detta interface och tilldela det till[`UserPromptRespondent`](../fieldoptions/userpromptrespondent/) egenskap för att etablera interaktion mellan fältet update och användaren.

### Exempel

Visar hur man skapar ett ASK-fält och ställer in dess egenskaper.

```csharp
[Test]
public void FieldAsk()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Placera ett fält där svaret på vårt ASK-fält kommer att placeras.
    FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
    fieldRef.BookmarkName = "MyAskField";
    builder.Writeln();

    Assert.AreEqual(" REF  MyAskField", fieldRef.GetFieldCode());

    // Infoga ASK-fältet och redigera dess egenskaper för att referera till vårt REF-fält med bokmärkesnamn.
    FieldAsk fieldAsk = (FieldAsk)builder.InsertField(FieldType.FieldAsk, true);
    fieldAsk.BookmarkName = "MyAskField";
    fieldAsk.PromptText = "Please provide a response for this ASK field";
    fieldAsk.DefaultResponse = "Response from within the field.";
    fieldAsk.PromptOnceOnMailMerge = true;
    builder.Writeln();

    Assert.AreEqual(
        " ASK  MyAskField \"Please provide a response for this ASK field\" \\d \"Response from within the field.\" \\o",
        fieldAsk.GetFieldCode());

    // ASK-fält tillämpar standardsvaret på sina respektive REF-fält under en e-postkoppling.
    DataTable table = new DataTable("My Table");
    table.Columns.Add("Column 1");
    table.Rows.Add("Row 1");
    table.Rows.Add("Row 2");

    FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    fieldMergeField.FieldName = "Column 1";

    // Vi kan ändra eller åsidosätta standardsvaret i våra ASK-fält med en anpassad promptsvarare,
    // som kommer att inträffa under en e-postkoppling.
    doc.FieldOptions.UserPromptRespondent = new MyPromptRespondent();
    doc.MailMerge.Execute(table);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.ASK.docx");

/// <summary>
/// Lägger text framför standardsvaret i ett ASK-fält under en e-postkoppling.
/// </summary>
private class MyPromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response from MyPromptRespondent. " + defaultResponse;
    }
}
```

### Se även

* namnutrymme [Aspose.Words.Fields](../../aspose.words.fields/)
* hopsättning [Aspose.Words](../../)


