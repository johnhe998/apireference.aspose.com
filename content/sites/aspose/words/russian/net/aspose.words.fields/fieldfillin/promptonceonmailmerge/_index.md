---
title: FieldFillIn.PromptOnceOnMailMerge
second_title: Справочник по API Aspose.Words для .NET
description: FieldFillIn свойство. Получает или задает должен ли ответ пользователя быть получен один раз за операцию слияния.
type: docs
weight: 30
url: /ru/net/aspose.words.fields/fieldfillin/promptonceonmailmerge/
---
## FieldFillIn.PromptOnceOnMailMerge property

Получает или задает, должен ли ответ пользователя быть получен один раз за операцию слияния.

```csharp
public bool PromptOnceOnMailMerge { get; set; }
```

### Примеры

Показывает, как использовать поле FILLIN для запроса ответа у пользователя.

```csharp
public void FieldFillIn()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Вставить поле FILLIN. Когда мы вручную обновляем это поле в Microsoft Word,
    // это предложит нам ввести ответ. После этого поле отобразит ответ в виде текста.
    FieldFillIn field = (FieldFillIn)builder.InsertField(FieldType.FieldFillIn, true);
    field.PromptText = "Please enter a response:";
    field.DefaultResponse = "A default response.";

    // Мы также можем использовать эти поля, чтобы запросить у пользователя уникальный ответ для каждой страницы
    // создано во время слияния почты, выполненного с помощью Microsoft Word.
    field.PromptOnceOnMailMerge = true;

    Assert.AreEqual(" FILLIN  \"Please enter a response:\" \\d \"A default response.\" \\o", field.GetFieldCode());

    FieldMergeField mergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    mergeField.FieldName = "MergeField";

    // Если мы выполняем слияние программно, мы можем использовать настраиваемый ответчик приглашения
    // для автоматического редактирования ответов для полей FILLIN, которые встречаются при слиянии.
    doc.FieldOptions.UserPromptRespondent = new PromptRespondent();
    doc.MailMerge.Execute(new [] { "MergeField" }, new object[] { "" });

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.FILLIN.docx");

/// <summary>
/// Добавляет строку к ответу по умолчанию для каждого поля FILLIN во время слияния.
/// </summary>
private class PromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response modified by PromptRespondent. " + defaultResponse;
    }
}
```

### Смотрите также

* class [FieldFillIn](../)
* пространство имен [Aspose.Words.Fields](../../fieldfillin/)
* сборка [Aspose.Words](../../../)


