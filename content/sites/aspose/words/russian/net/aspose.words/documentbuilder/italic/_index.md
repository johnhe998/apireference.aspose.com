---
title: DocumentBuilder.Italic
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder свойство. Истинно если шрифт отформатирован как курсив.
type: docs
weight: 120
url: /ru/net/aspose.words/documentbuilder/italic/
---
## DocumentBuilder.Italic property

Истинно, если шрифт отформатирован как курсив.

```csharp
public bool Italic { get; set; }
```

### Примеры

Показывает, как заполнить поля MERGEFIELD данными с помощью построителя документов вместо слияния.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем несколько MERGEFIELDS, которые принимают данные из столбцов с тем же именем в источнике данных во время слияния почты,
// и затем заполнить их вручную.
builder.InsertField(" MERGEFIELD Chairman ");
builder.InsertField(" MERGEFIELD ChiefFinancialOfficer ");
builder.InsertField(" MERGEFIELD ChiefTechnologyOfficer ");

builder.MoveToMergeField("Chairman");
builder.Bold = true;
builder.Writeln("John Doe");

builder.MoveToMergeField("ChiefFinancialOfficer");
builder.Italic = true;
builder.Writeln("Jane Doe");

builder.MoveToMergeField("ChiefTechnologyOfficer");
builder.Italic = true;
builder.Writeln("John Bloggs");

doc.Save(ArtifactsDir + "DocumentBuilder.FillMergeFields.docx");
```

### Смотрите также

* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


