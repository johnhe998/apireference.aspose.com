---
title: FieldChar.GetField
second_title: Справочник по API Aspose.Words для .NET
description: FieldChar метод. Возвращает поле для поля char.
type: docs
weight: 40
url: /ru/net/aspose.words.fields/fieldchar/getfield/
---
## FieldChar.GetField method

Возвращает поле для поля char.

```csharp
public Field GetField()
```

### Возвращаемое значение

Поле для поля char.

### Примечания

Новый[`Field`](../../field/) объект создается каждый раз при вызове метода.

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

* class [Field](../../field/)
* class [FieldChar](../)
* пространство имен [Aspose.Words.Fields](../../fieldchar/)
* сборка [Aspose.Words](../../../)


