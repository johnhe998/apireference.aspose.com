---
title: FieldInfo.InfoType
second_title: Справочник по API Aspose.Words для .NET
description: FieldInfo свойство. Получает или задает тип вставляемого свойства документа.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldinfo/infotype/
---
## FieldInfo.InfoType property

Получает или задает тип вставляемого свойства документа.

```csharp
public string InfoType { get; set; }
```

### Примеры

Показывает, как работать с полями INFO.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Установите значение для встроенного свойства «Комментарии», а затем вставьте поле INFO для отображения значения этого свойства.
doc.BuiltInDocumentProperties.Comments = "My comment";
FieldInfo field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.Update();

Assert.AreEqual(" INFO  Comments", field.GetFieldCode());
Assert.AreEqual("My comment", field.Result);

builder.Writeln();

// Установка значения для свойства NewValue поля и обновление
// поле также перезапишет соответствующее встроенное свойство новым значением.
field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.NewValue = "New comment";
field.Update();

Assert.AreEqual(" INFO  Comments \"New comment\"", field.GetFieldCode());
Assert.AreEqual("New comment", field.Result);
Assert.AreEqual("New comment", doc.BuiltInDocumentProperties.Comments);

doc.Save(ArtifactsDir + "Field.INFO.docx");
```

### Смотрите также

* class [FieldInfo](../)
* пространство имен [Aspose.Words.Fields](../../fieldinfo/)
* сборка [Aspose.Words](../../../)


