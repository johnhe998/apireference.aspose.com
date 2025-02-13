---
title: Document.NormalizeFieldTypes
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Изменяет значения типа поляFieldType изFieldStart FieldSeparator FieldEnd во всем документе чтобы они соответствовали типам полей содержащимся в кодах полей.
type: docs
weight: 610
url: /ru/net/aspose.words/document/normalizefieldtypes/
---
## Document.NormalizeFieldTypes method

Изменяет значения типа поля[`FieldType`](../../../aspose.words.fields/fieldchar/fieldtype/) из[`FieldStart`](../../../aspose.words.fields/fieldstart/) ,[`FieldSeparator`](../../../aspose.words.fields/fieldseparator/) ,[`FieldEnd`](../../../aspose.words.fields/fieldend/) во всем документе, чтобы они соответствовали типам полей, содержащимся в кодах полей.

```csharp
public void NormalizeFieldTypes()
```

### Примечания

Используйте этот метод после изменений документа, влияющих на типы полей.

Чтобы изменить значения типа поля в определенной части документа, используйте[`NormalizeFieldTypes`](../../range/normalizefieldtypes/).

### Примеры

Показывает, как обновить тип поля с помощью его кода поля.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE", null);

// Aspose.Words автоматически определяет типы полей на основе кодов полей.
Assert.AreEqual(FieldType.FieldDate, field.Type);

// Вручную изменить необработанный текст поля, который определяет код поля.
Run fieldText = (Run)doc.FirstSection.Body.FirstParagraph.GetChildNodes(NodeType.Run, true)[0];

// Изменение кода поля изменило это поле на одно другого типа,
// но свойства типа поля по-прежнему отображают старый тип.
Assert.AreEqual("PAGE", field.GetFieldCode());
Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual(FieldType.FieldDate, field.Start.FieldType);
Assert.AreEqual(FieldType.FieldDate, field.Separator.FieldType);
Assert.AreEqual(FieldType.FieldDate, field.End.FieldType);

// Обновите эти свойства с помощью этого метода, чтобы отобразить текущее значение.
doc.NormalizeFieldTypes();

Assert.AreEqual(FieldType.FieldPage, field.Type);
Assert.AreEqual(FieldType.FieldPage, field.Start.FieldType);
Assert.AreEqual(FieldType.FieldPage, field.Separator.FieldType); 
Assert.AreEqual(FieldType.FieldPage, field.End.FieldType);
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


