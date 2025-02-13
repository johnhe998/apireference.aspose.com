---
title: FieldMergingArgsBase.FieldName
second_title: Справочник по API Aspose.Words для .NET
description: FieldMergingArgsBase свойство. Получает имя поля слияния в источнике данных.
type: docs
weight: 40
url: /ru/net/aspose.words.mailmerging/fieldmergingargsbase/fieldname/
---
## FieldMergingArgsBase.FieldName property

Получает имя поля слияния в источнике данных.

```csharp
public string FieldName { get; }
```

### Примечания

Если у вас есть сопоставление имени поля документа с другим именем поля источника данных, , то это имя сопоставленного поля.

Если вы указали в документе префикс имени поля, например «Image:MyFieldName», , то **Имя поля** возвращает имя поля без префикса, то есть "MyFieldName".

### Примеры

Показывает, как вставлять поля формы флажка в поля MERGEFIELD в качестве данных слияния во время слияния почты.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Используйте MERGEFIELD с тегами "TableStart"/"TableEnd" для определения области слияния почты
    // который принадлежит источнику данных с именем "StudentCourse" и имеет поле MERGEFIELD, которое принимает данные из столбца с именем "CourseName".
    builder.StartTable();
    builder.InsertCell();
    builder.InsertField(" MERGEFIELD  TableStart:StudentCourse ");
    builder.InsertCell();
    builder.InsertField(" MERGEFIELD  CourseName ");
    builder.InsertCell();
    builder.InsertField(" MERGEFIELD  TableEnd:StudentCourse ");
    builder.EndTable();

    doc.MailMerge.FieldMergingCallback = new HandleMergeFieldInsertCheckBox();

    DataTable dataTable = GetStudentCourseDataTable();

    doc.MailMerge.ExecuteWithRegions(dataTable);
    doc.Save(ArtifactsDir + "MailMergeEvent.InsertCheckBox.docx");

/// <summary>
/// При обнаружении MERGEFIELD с определенным именем вставляет поле формы флажка вместо текста данных слияния.
/// </summary>
private class HandleMergeFieldInsertCheckBox : IFieldMergingCallback
{
    /// <summary>
    /// Вызывается, когда слияние почты объединяет данные в MERGEFIELD.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "CourseName")
        {
            Assert.AreEqual("StudentCourse", args.TableName);

            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.FieldName);
            builder.InsertCheckBox(args.DocumentFieldName + mCheckBoxCount, false, 0);

            string fieldValue = args.FieldValue.ToString();

            // В этом случае для каждой записи с индексом 'n' соответствующее значение поля равно "Курс n".
            Assert.AreEqual(char.GetNumericValue(fieldValue[7]), args.RecordIndex);

            builder.Write(fieldValue);
            mCheckBoxCount++;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // Ничего не делать.
    }

    private int mCheckBoxCount;
}

/// <summary>
/// Создает источник данных слияния почты.
/// </summary>
private static DataTable GetStudentCourseDataTable()
{
    DataTable dataTable = new DataTable("StudentCourse");
    dataTable.Columns.Add("CourseName");
    for (int i = 0; i < 10; i++)
    {
        DataRow datarow = dataTable.NewRow();
        dataTable.Rows.Add(datarow);
        datarow[0] = "Course " + i;
    }

    return dataTable;
}
```

### Смотрите также

* class [FieldMergingArgsBase](../)
* пространство имен [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* сборка [Aspose.Words](../../../)


