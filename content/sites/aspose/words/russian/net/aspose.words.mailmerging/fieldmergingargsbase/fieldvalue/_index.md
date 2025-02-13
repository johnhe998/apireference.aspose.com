---
title: FieldMergingArgsBase.FieldValue
second_title: Справочник по API Aspose.Words для .NET
description: FieldMergingArgsBase свойство. Получает или задает значение поля из источника данных.
type: docs
weight: 50
url: /ru/net/aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/
---
## FieldMergingArgsBase.FieldValue property

Получает или задает значение поля из источника данных.

```csharp
public object FieldValue { get; set; }
```

### Примечания

Это свойство содержит значение, которое только что было выбрано из вашего источника данных для этого поля механизмом слияния. Вы также можете заменить значение, установив свойство .

### Примеры

Показывает, как редактировать значения, которые поля MERGEFIELD получают при слиянии почты.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Вставьте несколько полей MERGEFIELD с переключателями формата, которые будут редактировать значения, которые они получат во время слияния.
    builder.InsertField("MERGEFIELD text_Field1 \\* Caps", null);
    builder.Write(", ");
    builder.InsertField("MERGEFIELD text_Field2 \\* Upper", null);
    builder.Write(", ");
    builder.InsertField("MERGEFIELD numeric_Field1 \\# 0.0", null);

    builder.Document.MailMerge.FieldMergingCallback = new FieldValueMergingCallback();

    builder.Document.MailMerge.Execute(
        new string[] { "text_Field1", "text_Field2", "numeric_Field1" },
        new object[] { "Field 1", "Field 2", 10 });
    string t = doc.GetText().Trim();
    Assert.AreEqual("Merge Value For \"Text_Field1\": Field 1, MERGE VALUE FOR \"TEXT_FIELD2\": FIELD 2, 10000.0", doc.GetText().Trim());
}

/// <summary>
/// Редактирует значения, которые поля MERGEFIELD получают во время слияния почты.
/// Имя MERGEFIELD должно иметь префикс, чтобы этот обратный вызов воздействовал на его значение.
/// </summary>
private class FieldValueMergingCallback : IFieldMergingCallback
{
    /// <summary>
    /// Вызывается, когда слияние почты объединяет данные в MERGEFIELD.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs e)
    {
        if (e.FieldName.StartsWith("text_"))
            e.FieldValue = $"Merge value for \"{e.FieldName}\": {(string)e.FieldValue}";
        else if (e.FieldName.StartsWith("numeric_"))
            e.FieldValue = (int)e.FieldValue * 1000;
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        // Ничего не делать.
    }
}
```

### Смотрите также

* class [FieldMergingArgsBase](../)
* пространство имен [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* сборка [Aspose.Words](../../../)


