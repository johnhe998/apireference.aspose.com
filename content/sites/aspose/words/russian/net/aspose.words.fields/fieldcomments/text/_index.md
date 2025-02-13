---
title: FieldComments.Text
second_title: Справочник по API Aspose.Words для .NET
description: FieldComments свойство. Получает или задает текст комментариев.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldcomments/text/
---
## FieldComments.Text property

Получает или задает текст комментариев.

```csharp
public string Text { get; set; }
```

### Примеры

Показывает, как использовать поле COMMENTS.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Установите значение для встроенного свойства документа «Комментарии».
doc.BuiltInDocumentProperties.Comments = "My comment.";

// Создайте поле COMMENTS для отображения значения этого встроенного свойства.
FieldComments field = (FieldComments)builder.InsertField(FieldType.FieldComments, true);
field.Update();

Assert.AreEqual(" COMMENTS ", field.GetFieldCode());
Assert.AreEqual("My comment.", field.Result);

// Если мы зададим значение свойства Text поля COMMENTS и обновим его, поле будет
// перезаписываем текущее значение встроенного свойства "Комментарии" значением его свойства Текст,
// и затем отображаем новое значение.
field.Text = "My overriding comment.";
field.Update();

Assert.AreEqual(" COMMENTS  \"My overriding comment.\"", field.GetFieldCode());
Assert.AreEqual("My overriding comment.", field.Result);

doc.Save(ArtifactsDir + "Field.COMMENTS.docx");
```

### Смотрите также

* class [FieldComments](../)
* пространство имен [Aspose.Words.Fields](../../fieldcomments/)
* сборка [Aspose.Words](../../../)


