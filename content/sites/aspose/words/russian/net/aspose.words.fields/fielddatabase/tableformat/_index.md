---
title: FieldDatabase.TableFormat
second_title: Справочник по API Aspose.Words для .NET
description: FieldDatabase свойство. Получает или задает формат который должен применяться к результату запроса к базе данных.
type: docs
weight: 100
url: /ru/net/aspose.words.fields/fielddatabase/tableformat/
---
## FieldDatabase.TableFormat property

Получает или задает формат, который должен применяться к результату запроса к базе данных.

```csharp
public string TableFormat { get; set; }
```

### Примеры

Показывает, как извлечь данные из базы данных и вставить их как поле в документ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Это поле DATABASE будет запускать запрос к базе данных и отображать результат в таблице.
FieldDatabase field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query = "SELECT * FROM [Products]";

Assert.AreEqual($" DATABASE  \\d \"{DatabaseDir.Replace("\\", "\\\\") + "Northwind.mdb"}\" \\c \"DSN=MS Access Databases\" \\s \"SELECT * FROM [Products]\"", 
    field.GetFieldCode());

// Вставьте еще одно поле DATABASE с более сложным запросом, который сортирует все продукты в порядке убывания по валовым продажам.
field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query =
    "SELECT [Products].ProductName, FORMAT(SUM([Order Details].UnitPrice * (1 - [Order Details].Discount) * [Order Details].Quantity), 'Currency') AS GrossSales " +
    "FROM([Products] " +
    "LEFT JOIN[Order Details] ON[Products].[ProductID] = [Order Details].[ProductID]) " +
    "GROUP BY[Products].ProductName " +
    "ORDER BY SUM([Order Details].UnitPrice* (1 - [Order Details].Discount) * [Order Details].Quantity) DESC";

// Эти свойства имеют ту же функцию, что и предложения LIMIT и TOP.
// Настройте их для отображения только строк с 1 по 10 результата запроса в таблице поля.
field.FirstRecord = "1";
field.LastRecord = "10";

// Это свойство является индексом формата, который мы хотим использовать для нашей таблицы. Список форматов таблиц находится в меню "Автоформат таблицы..."
// это появляется, когда мы создаем поле DATABASE в Microsoft Word. Индекс №10 соответствует формату «Красочный 3».
field.TableFormat = "10";

// Свойство FormatAttribute представляет собой строковое представление целого числа, которое хранит несколько флагов.
// Мы можем по-отечески применить формат, на который указывает свойство TableFormat, установив в этом свойстве разные флаги.
// Число, которое мы используем, является суммой комбинации значений, соответствующих различным аспектам стиля таблицы.
// 63 представляет 1 (границы) + 2 (затенение) + 4 (шрифт) + 8 (цвет) + 16 (автоподгонка) + 32 (строки заголовков).
field.FormatAttributes = "63";
field.InsertHeadings = true;
field.InsertOnceOnMailMerge = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATABASE.docx");
```

### Смотрите также

* class [FieldDatabase](../)
* пространство имен [Aspose.Words.Fields](../../fielddatabase/)
* сборка [Aspose.Words](../../../)


