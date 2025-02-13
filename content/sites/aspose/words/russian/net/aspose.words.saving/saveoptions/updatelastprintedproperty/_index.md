---
title: SaveOptions.UpdateLastPrintedProperty
second_title: Справочник по API Aspose.Words для .NET
description: SaveOptions свойство. Получает или задает значение определяющееLastPrinted свойство обновляется перед сохранением.
type: docs
weight: 180
url: /ru/net/aspose.words.saving/saveoptions/updatelastprintedproperty/
---
## SaveOptions.UpdateLastPrintedProperty property

Получает или задает значение, определяющее,[`LastPrinted`](../../../aspose.words.properties/builtindocumentproperties/lastprinted/) свойство обновляется перед сохранением.

```csharp
public bool UpdateLastPrintedProperty { get; set; }
```

### Примеры

Показывает, как обновить свойство «CreatedTime» документа при сохранении.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.CreatedTime = new DateTime(2019, 12, 20);

// Этот флаг определяет, обновляется ли созданное время, которое является встроенным свойством.
// Если да, то дата последней операции сохранения документа
// с этим объектом SaveOptions, переданным в качестве параметра, используется как время создания.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateCreatedTimeProperty = isUpdateCreatedTimeProperty;

doc.Save(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx", saveOptions);

// Откройте сохраненный документ, затем проверьте значение свойства.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx");

Assert.AreNotEqual(isUpdateCreatedTimeProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.CreatedTime);
```

Показывает, как обновить свойство «Последний напечатанный» документа при сохранении.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.LastPrinted = new DateTime(2019, 12, 20);

// Этот флаг определяет, обновляется ли последняя напечатанная дата, которая является встроенным свойством.
// Если да, то дата последней операции сохранения документа
// с этим объектом SaveOptions, переданным в качестве параметра, используется как дата печати.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateLastPrintedProperty = isUpdateLastPrintedProperty;

// В Microsoft Word 2003 это свойство можно найти через Файл -> Свойства -> Статистика -> Напечатано.
// Его также можно отобразить в теле документа с помощью поля PRINTDATE.
doc.Save(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc", saveOptions);

// Откройте сохраненный документ, затем проверьте значение свойства.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc");

Assert.AreNotEqual(isUpdateLastPrintedProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.LastPrinted);
```

### Смотрите также

* class [SaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../saveoptions/)
* сборка [Aspose.Words](../../../)


