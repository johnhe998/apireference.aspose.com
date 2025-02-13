---
title: Применить форматирование строк
linktitle: Применить форматирование строк
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по применению форматирования строк к таблице с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

В этом руководстве мы пошагово проведем вас через процесс применения форматирования строк к таблице с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. К концу этого руководства у вас будет четкое представление о том, как форматировать строки таблицы в документах Word с помощью Aspose.Words для .NET.

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где вы хотите сохранить отредактированный документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создайте новый документ и построитель документов
 Далее необходимо создать новый экземпляр`Document` класс и конструктор документа для этого документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Создайте новую доску
 Чтобы применить форматирование строки, мы должны сначала создать новую таблицу, используя`StartTable()` метод конструктора документа.

```csharp
Table table = builder. StartTable();
```

## Шаг 4: Вставьте ячейку и перейдите к формату строки
Теперь мы можем вставить ячейку в таблицу и получить доступ к формату строки для этой ячейки с помощью конструктора документов.`InsertCell()` и`RowFormat` методы.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Шаг 5: Установите высоту строки
 Чтобы установить высоту строки, мы используем`Height` и`HeightRule` свойства формата строки. В этом примере мы устанавливаем высоту строки 100 пунктов и используем`Exactly` правило.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Шаг 6: Определите форматирование таблицы
 Некоторые свойства форматирования можно задать для самой таблицы, и они применяются ко всем строкам таблицы. В этом примере мы устанавливаем свойства поля таблицы с помощью`LeftPadding`, `RightPadding`, `TopPadding` и`BottomPadding` характеристики.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Шаг 7. Добавьте содержимое в строку
Теперь мы можем

 Мы собираемся добавить содержимое в строку, используя методы конструктора документа. В этом примере мы используем`Writeln()` метод добавления текста в строку.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Шаг 8: Завершите линию и таблицу
 Как только мы добавили содержимое в строку, мы можем закончить строку, используя`EndRow()` метод, а затем завершите таблицу, используя`EndTable()` метод.

```csharp
builder. EndRow();
builder. EndTable();
```

## Шаг 9: Сохраните измененный документ
Наконец, мы сохраняем измененный документ в файл. Вы можете выбрать подходящее имя и место для выходного документа.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Поздравляем! Теперь вы применили форматирование строк к таблице с помощью Aspose.Words для .NET.

### Пример исходного кода для применения форматирования строк с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Эти свойства форматирования задаются для таблицы и применяются ко всем строкам в таблице.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Заключение
В этом руководстве мы узнали, как применить форматирование строк к таблице с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко интегрировать эту функциональность в свои проекты C#. Управление форматированием строк таблицы является важным аспектом обработки документов, и Aspose.Words предлагает для этого мощный и гибкий API. Обладая этими знаниями, вы сможете улучшить визуальное представление своих документов Word и выполнить определенные требования.