---
title: Odso.FirstRowContainsColumnNames
second_title: Справочник по API Aspose.Words для .NET
description: Odso свойство. Указывает что хостприложение должно обрабатывать первую строку данных в указанном внешнем источнике data как строку заголовка содержащую имена каждого столбца в источнике данных. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 60
url: /ru/net/aspose.words.settings/odso/firstrowcontainscolumnnames/
---
## Odso.FirstRowContainsColumnNames property

Указывает, что хост-приложение должно обрабатывать первую строку данных в указанном внешнем источнике data как строку заголовка, содержащую имена каждого столбца в источнике данных. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool FirstRowContainsColumnNames { get; set; }
```

### Примечания

РК Я никогда не видел это в использовании.

### Примеры

Показывает, как выполнить слияние почты с данными из объекта источника данных Office.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// Создаем источник данных в виде ASCII-файла с символом "|" персонаж
// действует как разделитель, разделяющий столбцы. Первая строка содержит имена трех столбцов,
// и каждая последующая строка представляет собой строку с соответствующими значениями.
string[] lines = { "FirstName|LastName|Message",
    "John|Doe|Hello! This message was created with Aspose Words mail merge." };
string dataSrcFilename = ArtifactsDir + "MailMerge.MailMergeSettings.DataSource.txt";

File.WriteAllLines(dataSrcFilename, lines);

MailMergeSettings settings = doc.MailMergeSettings;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.CheckErrors = MailMergeCheckErrors.Simulate;
settings.DataType = MailMergeDataType.Native;
settings.DataSource = dataSrcFilename;
settings.Query = "SELECT * FROM " + doc.MailMergeSettings.DataSource;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

Assert.AreEqual(MailMergeDestination.Default, settings.Destination);
Assert.False(settings.DoNotSupressBlankLines);

Odso odso = settings.Odso;
odso.DataSource = dataSrcFilename;
odso.DataSourceType = OdsoDataSourceType.Text;
odso.ColumnDelimiter = '|';
odso.FirstRowContainsColumnNames = true;

Assert.AreNotSame(odso, odso.Clone());
Assert.AreNotSame(settings, settings.Clone());

// Открытие этого документа в Microsoft Word приведет к выполнению слияния перед отображением содержимого. 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### Смотрите также

* class [Odso](../)
* пространство имен [Aspose.Words.Settings](../../odso/)
* сборка [Aspose.Words](../../../)


