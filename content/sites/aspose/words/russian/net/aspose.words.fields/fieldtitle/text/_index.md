---
title: FieldTitle.Text
second_title: Справочник по API Aspose.Words для .NET
description: FieldTitle свойство. Получает или задает текст заголовка.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldtitle/text/
---
## FieldTitle.Text property

Получает или задает текст заголовка.

```csharp
public string Text { get; set; }
```

### Примеры

Показывает, как использовать поле TITLE.

```csharp
Document doc = new Document();

 // Задаем значение для встроенного свойства документа "Заголовок".
doc.BuiltInDocumentProperties.Title = "My Title";

// Мы можем использовать поле TITLE для отображения значения этого свойства в документе.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldTitle field = (FieldTitle)builder.InsertField(FieldType.FieldTitle, false);
field.Update();

Assert.AreEqual(" TITLE ", field.GetFieldCode());
Assert.AreEqual("My Title", field.Result);

// Установка значения для свойства Text поля,
// и последующее обновление поля также перезапишет соответствующее встроенное свойство новым значением.
builder.Writeln();
field = (FieldTitle)builder.InsertField(FieldType.FieldTitle, false);
field.Text = "My New Title";
field.Update();

Assert.AreEqual(" TITLE  \"My New Title\"", field.GetFieldCode());
Assert.AreEqual("My New Title", field.Result);
Assert.AreEqual("My New Title", doc.BuiltInDocumentProperties.Title);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TITLE.docx");
```

### Смотрите также

* class [FieldTitle](../)
* пространство имен [Aspose.Words.Fields](../../fieldtitle/)
* сборка [Aspose.Words](../../../)


