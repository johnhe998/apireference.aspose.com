---
title: FieldMergeField.IsMapped
second_title: Aspose.Words für .NET-API-Referenz
description: FieldMergeField eigendom. Ruft ab oder legt fest ob dieses Feld ein zugeordnetes Feld ist.
type: docs
weight: 30
url: /de/net/aspose.words.fields/fieldmergefield/ismapped/
---
## FieldMergeField.IsMapped property

Ruft ab oder legt fest, ob dieses Feld ein zugeordnetes Feld ist.

```csharp
public bool IsMapped { get; set; }
```

### Beispiele

Zeigt, wie MERGEFIELD-Felder verwendet werden, um einen Seriendruck durchzuführen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Datentabelle, die als Datenquelle für den Seriendruck verwendet werden soll.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Ein MERGEFIELD mit einer FieldName-Eigenschaft einfügen, die auf den Namen einer Spalte in der Datenquelle gesetzt ist.
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Courtesy Title";
fieldMergeField.IsMapped = true;
fieldMergeField.IsVerticalFormatting = false;

// Wir können Text vor und nach dem Wert anwenden, den dieses Feld akzeptiert, wenn die Zusammenführung stattfindet.
fieldMergeField.TextBefore = "Dear ";
fieldMergeField.TextAfter = " ";

Assert.AreEqual(" MERGEFIELD  \"Courtesy Title\" \\m \\b \"Dear \" \\f \" \"", fieldMergeField.GetFieldCode());

// Ein weiteres MERGEFIELD für eine andere Spalte in der Datenquelle einfügen.
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Last Name";
fieldMergeField.TextAfter = ":";

doc.UpdateFields();
doc.MailMerge.Execute(table);

Assert.AreEqual("Dear Mr. Doe:\u000cDear Mrs. Cardholder:", doc.GetText().Trim());
```

### Siehe auch

* class [FieldMergeField](../)
* namensraum [Aspose.Words.Fields](../../fieldmergefield/)
* Montage [Aspose.Words](../../../)


