---
title: MailMerge.UseNonMergeFields
second_title: Справочник по API Aspose.Words для .NET
description: MailMerge свойство. При значении true указывает что в дополнение к полям MERGEFIELD слияние выполняется с некоторыми другими типами полей и также с тегами fieldName.
type: docs
weight: 150
url: /ru/net/aspose.words.mailmerging/mailmerge/usenonmergefields/
---
## MailMerge.UseNonMergeFields property

При значении true указывает, что в дополнение к полям MERGEFIELD слияние выполняется с некоторыми другими типами полей и также с тегами "{{fieldName}}".

```csharp
public bool UseNonMergeFields { get; set; }
```

### Примечания

Обычно слияние почты выполняется только в полях MERGEFIELD, но несколько клиентов создали свои report с использованием других полей и таким образом создали множество документов. Для упрощения миграции (и поскольку этот подход использовался несколькими клиентами независимо друг от друга) была введена возможность слияния почты с другими полями.

Когда **Усенонмержефиелдс** установлено значение true, Aspose.Words будет выполнять слияние почты в следующие поля:

MERGEFIELD имя поля

MACROBUTTON NOMACRO Имя поля

ЕСЛИ 0 = 0 "{ИмяПоля}" ""

Кроме того, когда **UserNonMergeFields** установлено значение true, Aspose.Words будет выполнять слияние почты в текстовые теги tags "{{fieldName}}". Это не поля, а просто текстовые теги.

### Примеры

Показывает, как сохранить внешний вид альтернативных тегов слияния, которые не используются во время слияния.

```csharp
public void PreserveUnusedTags(bool preserveUnusedTags)
{
    Document doc = CreateSourceDocWithAlternativeMergeFields();
    DataTable dataTable = CreateSourceTablePreserveUnusedTags();

    // По умолчанию слияние помещает данные из каждой строки таблицы в поля MERGEFIELD, которые именуют столбцы в этой таблице. 
    // В нашем документе нет таких полей, но есть теги открытого текста, заключенные в фигурные скобки.
    // Если мы установим для флага "PreserveUnusedTags" значение "true", мы сможем рассматривать эти теги как MERGEFIELD
    // чтобы позволить нашему слиянию почты вставлять данные из источника данных в эти теги.
    // Если мы установим флаг "PreserveUnusedTags" в "false",
    // слияние конвертирует эти теги в поля MERGEFIELD и оставляет их незаполненными.
    doc.MailMerge.PreserveUnusedTags = preserveUnusedTags;
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.PreserveUnusedTags.docx");

    // В нашем документе есть тег для столбца с именем "Column2", которого нет в таблице.
    // Если мы установим флаг "PreserveUnusedTags" в "false", then the mail merge will convert this tag into a MERGEFIELD.
    Assert.AreEqual(doc.GetText().Contains("{{ Column2 }}"), preserveUnusedTags);

    if (preserveUnusedTags)
        Assert.AreEqual(0, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
    else
        Assert.AreEqual(1, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
}

/// <summary>
/// Создайте документ и добавьте два тега открытого текста, которые могут действовать как поля MERGEFIELD во время слияния.
/// </summary>
private static Document CreateSourceDocWithAlternativeMergeFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("{{ Column1 }}");
    builder.Writeln("{{ Column2 }}");

    // Наши теги будут регистрироваться как места назначения для данных слияния почты, только если мы установим для этого параметра значение true.
    doc.MailMerge.UseNonMergeFields = true;

    return doc;
}

/// <summary>
/// Создаем простую таблицу данных с одним столбцом.
/// </summary>
private static DataTable CreateSourceTablePreserveUnusedTags()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Rows.Add(new object[] { "Value1" });

    return dataTable;
}
```

### Смотрите также

* class [MailMerge](../)
* пространство имен [Aspose.Words.MailMerging](../../mailmerge/)
* сборка [Aspose.Words](../../../)


