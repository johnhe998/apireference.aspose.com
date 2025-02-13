---
title: FieldTemplate.IncludeFullPath
second_title: Справочник по API Aspose.Words для .NET
description: FieldTemplate свойство. Получает или задает следует ли включать полный путь к файлу.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldtemplate/includefullpath/
---
## FieldTemplate.IncludeFullPath property

Получает или задает, следует ли включать полный путь к файлу.

```csharp
public bool IncludeFullPath { get; set; }
```

### Примеры

Показывает, как использовать поле ШАБЛОН для отображения местоположения шаблона документа в локальной файловой системе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Мы можем установить имя шаблона, используя поля. Это свойство используется, когда «doc.AttachedTemplate» пуст.
// Если это свойство пусто, используется имя файла шаблона по умолчанию "Normal.dotm".
doc.FieldOptions.TemplateName = string.Empty;

FieldTemplate field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
Assert.AreEqual(" TEMPLATE ", field.GetFieldCode());

builder.Writeln();
field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
field.IncludeFullPath = true;

Assert.AreEqual(" TEMPLATE  \\p", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TEMPLATE.docx");
```

### Смотрите также

* class [FieldTemplate](../)
* пространство имен [Aspose.Words.Fields](../../fieldtemplate/)
* сборка [Aspose.Words](../../../)


