---
title: FieldMergeField.FieldNameNoPrefix
second_title: Aspose.Words för .NET API Referens
description: FieldMergeField fast egendom. Returnerar bara namnet på datafältet. Alla prefix tas bort till prefixegenskapen.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldmergefield/fieldnamenoprefix/
---
## FieldMergeField.FieldNameNoPrefix property

Returnerar bara namnet på datafältet. Alla prefix tas bort till prefixegenskapen.

```csharp
public string FieldNameNoPrefix { get; }
```

### Exempel

Visar hur man använder MERGEFIELD-fält för att utföra en e-postkoppling.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en datatabell som ska användas som en kopplingsdatakälla.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Infoga ett MERGEFIELD med en FieldName-egenskap inställd på namnet på en kolumn i datakällan.
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Courtesy Title";
fieldMergeField.IsMapped = true;
fieldMergeField.IsVerticalFormatting = false;

// Vi kan använda text före och efter värdet som detta fält accepterar när sammanslagningen sker.
fieldMergeField.TextBefore = "Dear ";
fieldMergeField.TextAfter = " ";

Assert.AreEqual(" MERGEFIELD  \"Courtesy Title\" \\m \\b \"Dear \" \\f \" \"", fieldMergeField.GetFieldCode());

// Infoga ytterligare ett MERGEFIELD för en annan kolumn i datakällan.
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Last Name";
fieldMergeField.TextAfter = ":";

doc.UpdateFields();
doc.MailMerge.Execute(table);

Assert.AreEqual("Dear Mr. Doe:\u000cDear Mrs. Cardholder:", doc.GetText().Trim());
```

### Se även

* class [FieldMergeField](../)
* namnutrymme [Aspose.Words.Fields](../../fieldmergefield/)
* hopsättning [Aspose.Words](../../../)


