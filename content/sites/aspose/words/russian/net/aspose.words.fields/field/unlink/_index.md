---
title: Field.Unlink
second_title: Справочник по API Aspose.Words для .NET
description: Field метод. Выполняет развязку поля.
type: docs
weight: 130
url: /ru/net/aspose.words.fields/field/unlink/
---
## Field.Unlink method

Выполняет развязку поля.

```csharp
public bool Unlink()
```

### Возвращаемое значение

`Истинный` если поле не было связано, в противном случае`ЛОЖЬ` .

### Примечания

Заменяет поле самым последним результатом.

Некоторые поля, такие как поля XE (запись индекса) и поля SEQ (последовательность), нельзя разъединить.

### Примеры

Показывает, как отменить связь поля.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
doc.Range.Fields[1].Unlink();
```

### Смотрите также

* class [Field](../)
* пространство имен [Aspose.Words.Fields](../../field/)
* сборка [Aspose.Words](../../../)


