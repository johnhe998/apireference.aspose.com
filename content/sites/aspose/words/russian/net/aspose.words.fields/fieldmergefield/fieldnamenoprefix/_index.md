---
title: FieldMergeField.FieldNameNoPrefix
second_title: Справочник по API Aspose.Words для .NET
description: FieldMergeField свойство. Возвращает только имя поля данных. Любой префикс разделяется на свойство префикса.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldmergefield/fieldnamenoprefix/
---
## FieldMergeField.FieldNameNoPrefix property

Возвращает только имя поля данных. Любой префикс разделяется на свойство префикса.

```csharp
public string FieldNameNoPrefix { get; }
```

### Примеры

Показывает, как использовать поля MERGEFIELD для выполнения слияния.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте таблицу данных, которая будет использоваться в качестве источника данных слияния.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Вставьте MERGEFIELD со свойством FieldName, для которого задано имя столбца в источнике данных.
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Courtesy Title";
fieldMergeField.IsMapped = true;
fieldMergeField.IsVerticalFormatting = false;

// Мы можем применить текст до и после значения, которое принимает это поле, когда происходит слияние.
fieldMergeField.TextBefore = "Dear ";
fieldMergeField.TextAfter = " ";

Assert.AreEqual(" MERGEFIELD  \"Courtesy Title\" \\m \\b \"Dear \" \\f \" \"", fieldMergeField.GetFieldCode());

// Вставить еще одно поле MERGEFIELD для другого столбца в источнике данных.
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Last Name";
fieldMergeField.TextAfter = ":";

doc.UpdateFields();
doc.MailMerge.Execute(table);

Assert.AreEqual("Dear Mr. Doe:\u000cDear Mrs. Cardholder:", doc.GetText().Trim());
```

### Смотрите также

* class [FieldMergeField](../)
* пространство имен [Aspose.Words.Fields](../../fieldmergefield/)
* сборка [Aspose.Words](../../../)


