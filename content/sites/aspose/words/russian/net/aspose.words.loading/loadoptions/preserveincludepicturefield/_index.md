---
title: LoadOptions.PreserveIncludePictureField
second_title: Справочник по API Aspose.Words для .NET
description: LoadOptions свойство. Получает или задает следует ли сохранять поле INCLUDEPICTURE при чтении форматов Microsoft Word. Значение по умолчанию  false.
type: docs
weight: 120
url: /ru/net/aspose.words.loading/loadoptions/preserveincludepicturefield/
---
## LoadOptions.PreserveIncludePictureField property

Получает или задает, следует ли сохранять поле INCLUDEPICTURE при чтении форматов Microsoft Word. Значение по умолчанию — false.

```csharp
public bool PreserveIncludePictureField { get; set; }
```

### Примечания

По умолчанию поле INCLUDEPICTURE преобразуется в объект формы. Вы можете переопределить это, если вам нужно сохранить поле, например, если вы хотите обновить его программно. Однако обратите внимание, что подход this не является обычным для Aspose.Words. Используйте его на свой страх и риск.

Одним из возможных вариантов использования может быть использование MERGEFIELD в качестве дочернего поля для динамического изменения исходного path изображения. В этом случае вам нужно сохранить INCLUDEPICTURE в модели.

### Примеры

Показывает, как сохранить или удалить поля INCLUDEPICTURE при загрузке документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldIncludePicture includePicture = (FieldIncludePicture)builder.InsertField(FieldType.FieldIncludePicture, true);
includePicture.SourceFullName = ImageDir + "Transparent background logo.png";
includePicture.Update(true);

using (MemoryStream docStream = new MemoryStream())
{
    doc.Save(docStream, new OoxmlSaveOptions(SaveFormat.Docx));

    // Мы можем установить флаг в объекте LoadOptions, чтобы решить, следует ли преобразовывать все поля INCLUDEPICTURE
    // в формы изображений при загрузке документа, который их содержит.
    LoadOptions loadOptions = new LoadOptions
    {
        PreserveIncludePictureField = preserveIncludePictureField
    };

    doc = new Document(docStream, loadOptions);

    if (preserveIncludePictureField)
    {
        Assert.True(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));

        doc.UpdateFields();
        doc.Save(ArtifactsDir + "Field.PreserveIncludePicture.docx");
    }
    else
    {
        Assert.False(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));
    }
}
```

### Смотрите также

* class [LoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../loadoptions/)
* сборка [Aspose.Words](../../../)


