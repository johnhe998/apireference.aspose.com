---
title: FieldGreetingLine.GetFieldNames
second_title: Справочник по API Aspose.Words для .NET
description: FieldGreetingLine метод. Возвращает коллекцию имен полей слияния используемых полем.
type: docs
weight: 50
url: /ru/net/aspose.words.fields/fieldgreetingline/getfieldnames/
---
## FieldGreetingLine.GetFieldNames method

Возвращает коллекцию имен полей слияния, используемых полем.

```csharp
public string[] GetFieldNames()
```

### Примеры

Показывает, как вставить поле GREETINGLINE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте общее приветствие, используя поле GREETINGLINE и некоторый текст после него.
FieldGreetingLine field = (FieldGreetingLine)builder.InsertField(FieldType.FieldGreetingLine, true);
builder.Writeln("\n\n\tThis is your custom greeting, created programmatically using Aspose Words!");

// Поле GREETINGLINE принимает значения из источника данных во время слияния почты, например MERGEFIELD.
// Он также может форматировать, как исходные данные записываются на свое место после завершения слияния.
// Коллекция имен полей соответствует столбцам из источника данных
// из которого поле будет принимать значения.
Assert.AreEqual(0, field.GetFieldNames().Length);

// Чтобы заполнить этот массив, нам нужно указать формат для нашей строки приветствия.
field.NameFormat = "<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> ";

// Теперь наше поле будет принимать значения из этих двух столбцов в источнике данных.
Assert.AreEqual("Courtesy Title", field.GetFieldNames()[0]);
Assert.AreEqual("Last Name", field.GetFieldNames()[1]);
Assert.AreEqual(2, field.GetFieldNames().Length);

// Эта строка будет охватывать любые случаи, когда данные таблицы данных недействительны
// заменив искаженное имя строкой.
field.AlternateText = "Sir or Madam";

// Установить локаль для форматирования результата.
field.LanguageId = new CultureInfo("en-US").LCID.ToString();

Assert.AreEqual(" GREETINGLINE  \\f \"<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> \" \\e \"Sir or Madam\" \\l 1033", 
    field.GetFieldCode());

// Создаем таблицу данных со столбцами, имена которых соответствуют элементам
// из коллекции имен полей, а затем выполнить слияние.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Эта строка имеет недопустимое значение в столбце «Заголовок любезности», поэтому наше приветствие по умолчанию будет иметь альтернативный текст.
table.Rows.Add("", "No", "Name");

doc.MailMerge.Execute(table);

Assert.That(doc.Range.Fields, Is.Empty);
Assert.AreEqual("Dear Mr. Doe,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Mrs. Cardholder,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Sir or Madam,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!",
    doc.GetText().Trim());
```

### Смотрите также

* class [FieldGreetingLine](../)
* пространство имен [Aspose.Words.Fields](../../fieldgreetingline/)
* сборка [Aspose.Words](../../../)


