---
title: LoadOptions.UpdateDirtyFields
second_title: Справочник по API Aspose.Words для .NET
description: LoadOptions свойство. Указывает обновлять ли поля сгрязный атрибут.
type: docs
weight: 160
url: /ru/net/aspose.words.loading/loadoptions/updatedirtyfields/
---
## LoadOptions.UpdateDirtyFields property

Указывает, обновлять ли поля с`грязный` атрибут.

```csharp
public bool UpdateDirtyFields { get; set; }
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

* class [LoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../loadoptions/)
* сборка [Aspose.Words](../../../)


