---
title: Field.IsDirty
second_title: Справочник по API Aspose.Words для .NET
description: Field свойство. Получает или устанавливает является ли текущий результат поля более неверным устаревшим изза других изменений внесенных в документ.
type: docs
weight: 40
url: /ru/net/aspose.words.fields/field/isdirty/
---
## Field.IsDirty property

Получает или устанавливает, является ли текущий результат поля более неверным (устаревшим) из-за других изменений, внесенных в документ.

```csharp
public bool IsDirty { get; set; }
```

### Примеры

Показывает, как использовать специальное свойство для обновления результата поля.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Присвойте документу встроенное значение свойства «Автор», а затем отобразите его с помощью поля.
doc.BuiltInDocumentProperties.Author = "John Doe";
FieldAuthor field = (FieldAuthor)builder.InsertField(FieldType.FieldAuthor, true);

Assert.False(field.IsDirty);
Assert.AreEqual("John Doe", field.Result);

// Обновить свойство. В поле по-прежнему отображается старое значение.
doc.BuiltInDocumentProperties.Author = "John & Jane Doe";

Assert.AreEqual("John Doe", field.Result);

// Так как значение поля устарело, мы можем пометить его как "грязное".
// Это значение останется устаревшим, пока мы не обновим поле вручную с помощью метода Field.Update().
field.IsDirty = true;

using (MemoryStream docStream = new MemoryStream())
{
    // Если мы сохраним, не вызывая метод обновления,
    // поле будет продолжать отображать устаревшее значение в выходном документе.
    doc.Save(docStream, SaveFormat.Docx);

    // Объект LoadOptions имеет возможность обновить все поля
    // отмечен как "грязный" при загрузке документа.
    LoadOptions options = new LoadOptions();
    options.UpdateDirtyFields = updateDirtyFields;
    doc = new Document(docStream, options);

    Assert.AreEqual("John & Jane Doe", doc.BuiltInDocumentProperties.Author);

    field = (FieldAuthor)doc.Range.Fields[0];

    // Обновление грязных полей, подобных этому, автоматически устанавливает для их флага "IsDirty" значение false.
    if (updateDirtyFields)
    {
        Assert.AreEqual("John & Jane Doe", field.Result);
        Assert.False(field.IsDirty);
    }
    else
    {
        Assert.AreEqual("John Doe", field.Result);
        Assert.True(field.IsDirty);
    }
}
```

### Смотрите также

* class [Field](../)
* пространство имен [Aspose.Words.Fields](../../field/)
* сборка [Aspose.Words](../../../)


