---
title: FieldMergeField.TextAfter
second_title: Справочник по API Aspose.Words для .NET
description: FieldMergeField свойство. Получает или задает текст который будет вставлен после поля если поле не пустое.
type: docs
weight: 50
url: /ru/net/aspose.words.fields/fieldmergefield/textafter/
---
## FieldMergeField.TextAfter property

Получает или задает текст, который будет вставлен после поля, если поле не пустое.

```csharp
public string TextAfter { get; set; }
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


