---
title: Вставить таблицу из HTML
linktitle: Вставить таблицу из HTML
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить таблицу из HTML в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/insert-table-from-html/
---

В этом уроке мы узнаем, как вставить таблицу в документ Word из HTML с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. К концу этого руководства вы сможете программно вставлять таблицы из HTML в документы Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Создание документа и инициализация генератора документов
Чтобы запустить Word Processing с документом и генератором документов, выполните следующие действия:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа
Document doc = new Document();

// Инициализировать генератор документов
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Вставка таблицы из HTML
Далее мы вставим таблицу в документ с помощью HTML-кода. Используйте следующий код:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Здесь мы используем`InsertHtml` метод конструктора документов для вставки HTML-кода, содержащего таблицу. Указанный HTML создает таблицу с двумя строками и двумя ячейками в каждой строке. Вы можете настроить содержимое таблицы, изменив HTML-код в соответствии с вашими потребностями.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с таблицей, вставленной из HTML. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для вставки таблицы из Html с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Обратите внимание, что AutoFitSettings не применяется к таблицам, вставленным из HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Заключение
В этом уроке мы узнали, как вставить таблицу в документ Word из HTML с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете программно вставлять таблицы из HTML в документы Word. Эта функция позволяет преобразовывать и импортировать табличные данные из источников HTML в документы Word.
