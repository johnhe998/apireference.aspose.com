---
title: Enum MailMergeDataType
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Settings.MailMergeDataType перечисление. Указывает тип внешнего источника данных слияния.
type: docs
weight: 5520
url: /ru/net/aspose.words.settings/mailmergedatatype/
---
## MailMergeDataType enumeration

Указывает тип внешнего источника данных слияния.

```csharp
public enum MailMergeDataType
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `-1` | Источник данных слияния не указан. |
| TextFile | `0` | Указывает, что данный документ был подключен к текстовому файлу через систему динамического обмена данными (DDE). |
| Database | `1` | Указывает, что данный документ был подключен к базе данных Access через систему динамического обмена данными (DDE). |
| Spreadsheet | `2` | Указывает, что данный документ был подключен к электронной таблице Excel через систему динамического обмена данными (DDE). |
| Query | `3` | Указывает, что данный документ был подключен к внешнему источнику данных с помощью внешнего инструмента запросов. |
| Odbc | `4` | Указывает, что данный документ был подключен к внешнему источнику данных через интерфейс Open Database Connectivity. |
| Native | `5` | Указывает, что данный документ был подключен к внешнему источнику данных через интерфейс объекта источника данных Office (ODSO). |
| Default | `-1` | равноNone . |

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

* property [DataType](../mailmergesettings/datatype/)
* пространство имен [Aspose.Words.Settings](../../aspose.words.settings/)
* сборка [Aspose.Words](../../)


