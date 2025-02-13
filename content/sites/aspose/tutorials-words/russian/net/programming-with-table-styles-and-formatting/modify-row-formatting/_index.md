---
title: Изменить форматирование строк
linktitle: Изменить форматирование строк
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по изменению форматирования строк таблицы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

В этом руководстве мы пошагово проведем вас через процесс изменения форматирования строки таблицы с помощью Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как изменить границы, высоту и разрыв строки строки таблицы в документах Word с помощью Aspose.Words для .NET.

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Здесь находится ваш документ Word. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите существующий документ
 Далее вам нужно загрузить существующий документ Word в экземпляр`Document` сорт.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Шаг 3: Доступ к строке для изменения
 Чтобы изменить форматирование строки таблицы, нам нужно перейти к определенной строке в таблице. Мы используем`GetChild()` и`FirstRow` методы для получения ссылки на первую строку таблицы.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Шаг 4. Измените формат строки
 Теперь мы можем изменить форматирование строки, используя свойства`RowFormat` сорт. Например, мы можем удалить границы строк, установить автоматическую высоту и разрешить разрыв строки.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Пример исходного кода для изменения форматирования строк с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Получить первую строку в таблице.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Заключение
В этом руководстве мы узнали, как изменить форматирование строки таблицы с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству, вы сможете легко настроить границы, высоту и разрыв строк в таблицах в документах Word. Aspose.Words предлагает мощный и гибкий API для управления и форматирования таблиц в ваших документах. Обладая этими знаниями, вы можете настроить визуальный макет своих таблиц в соответствии со своими конкретными потребностями.