---
title: IFieldUserPromptRespondent.Respond
second_title: Справочник по API Aspose.Words для .NET
description: IFieldUserPromptRespondent метод. При реализации возвращает ответ пользователя при запросе. Ваша реализация должна возвращать нулевой чтобы указать что пользователь не ответил на приглашение т. е. пользователь нажал кнопку Отмена в окне приглашения.
type: docs
weight: 10
url: /ru/net/aspose.words.fields/ifielduserpromptrespondent/respond/
---
## IFieldUserPromptRespondent.Respond method

При реализации возвращает ответ пользователя при запросе. Ваша реализация должна возвращать **нулевой** чтобы указать, что пользователь не ответил на приглашение (т. е. пользователь нажал кнопку «Отмена» в окне приглашения).

```csharp
public string Respond(string promptText, string defaultResponse)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| promptText | String | Текст подсказки (т.е. заголовок окна подсказки). |
| defaultResponse | String | Ответ пользователя по умолчанию (т. е. начальное значение, содержащееся в окне подсказки). |

### Возвращаемое значение

Ответ пользователя (т. е. подтвержденное значение, содержащееся в окне подсказки).

### Примеры

Показывает, как создать поле ASK и задать его свойства.

```csharp
[Test]
public void FieldAsk()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Разместите поле, где будет размещен ответ на наше поле ASK.
    FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
    fieldRef.BookmarkName = "MyAskField";
    builder.Writeln();

    Assert.AreEqual(" REF  MyAskField", fieldRef.GetFieldCode());

    // Вставьте поле ASK и отредактируйте его свойства, чтобы ссылаться на наше поле REF по имени закладки.
    FieldAsk fieldAsk = (FieldAsk)builder.InsertField(FieldType.FieldAsk, true);
    fieldAsk.BookmarkName = "MyAskField";
    fieldAsk.PromptText = "Please provide a response for this ASK field";
    fieldAsk.DefaultResponse = "Response from within the field.";
    fieldAsk.PromptOnceOnMailMerge = true;
    builder.Writeln();

    Assert.AreEqual(
        " ASK  MyAskField \"Please provide a response for this ASK field\" \\d \"Response from within the field.\" \\o",
        fieldAsk.GetFieldCode());

    // Поля ASK применяют ответ по умолчанию к соответствующим полям REF во время слияния.
    DataTable table = new DataTable("My Table");
    table.Columns.Add("Column 1");
    table.Rows.Add("Row 1");
    table.Rows.Add("Row 2");

    FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    fieldMergeField.FieldName = "Column 1";

    // Мы можем изменить или переопределить ответ по умолчанию в наших полях ASK с помощью пользовательского ответчика на подсказку,
    // что произойдет во время слияния почты.
    doc.FieldOptions.UserPromptRespondent = new MyPromptRespondent();
    doc.MailMerge.Execute(table);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.ASK.docx");

/// <summary>
/// Добавляет текст к ответу по умолчанию в поле ASK во время слияния.
/// </summary>
private class MyPromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response from MyPromptRespondent. " + defaultResponse;
    }
}
```

### Смотрите также

* interface [IFieldUserPromptRespondent](../)
* пространство имен [Aspose.Words.Fields](../../ifielduserpromptrespondent/)
* сборка [Aspose.Words](../../../)


