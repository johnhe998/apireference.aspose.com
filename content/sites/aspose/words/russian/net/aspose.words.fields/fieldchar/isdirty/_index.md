---
title: FieldChar.IsDirty
second_title: Справочник по API Aspose.Words для .NET
description: FieldChar свойство. Получает или устанавливает является ли текущий результат поля более неправильным устаревшим изза других изменений  внесенных в документ.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldchar/isdirty/
---
## FieldChar.IsDirty property

Получает или устанавливает, является ли текущий результат поля более неправильным (устаревшим) из-за других изменений , внесенных в документ.

```csharp
public bool IsDirty { get; set; }
```

### Примеры

Показывает, как работать с узлом FieldStart.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.Format.DateTimeFormat = "dddd, MMMM dd, yyyy";
field.Update();

FieldChar fieldStart = field.Start;

Assert.AreEqual(FieldType.FieldDate, fieldStart.FieldType);
Assert.AreEqual(false, fieldStart.IsDirty);
Assert.AreEqual(false, fieldStart.IsLocked);

// Получить объект фасада, представляющий поле в документе.
field = (FieldDate)fieldStart.GetField();

Assert.AreEqual(false, field.IsLocked);
Assert.AreEqual(" DATE  \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// Обновить поле, чтобы показать текущую дату.
field.Update();
```

### Смотрите также

* class [FieldChar](../)
* пространство имен [Aspose.Words.Fields](../../fieldchar/)
* сборка [Aspose.Words](../../../)


