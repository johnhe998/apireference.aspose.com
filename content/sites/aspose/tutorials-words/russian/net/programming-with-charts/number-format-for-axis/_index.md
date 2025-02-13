---
title: Числовой формат для оси на диаграмме
linktitle: Числовой формат для оси на диаграмме
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить числовой формат для оси на диаграмме с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/number-format-for-axis/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET, чтобы задать числовой формат для оси на диаграмме. В предоставленном исходном коде показано, как создать диаграмму, добавить ряд данных и отформатировать метки осей.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words for .NET. Вы можете загрузить его с помощью диспетчера пакетов NuGet для его установки.
- Путь к каталогу документа, в котором будет сохранен выходной документ.

## Шаг 2. Создайте новый документ и вставьте диаграмму

 Создать новый`Document` объект и`DocumentBuilder` для построения документа.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Далее используйте`InsertChart` метод`DocumentBuilder` чтобы вставить столбчатую диаграмму в документ.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте ряд данных на диаграмму.

Добавьте ряд данных на диаграмму. В этом примере мы добавим пять элементов с соответствующими значениями.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Шаг 4. Отформатируйте метки осей

 Чтобы установить числовой формат для меток оси Y, откройте`AxisY` свойство диаграммы и установить`NumberFormat.FormatCode` свойства в нужный формат. В этом примере мы устанавливаем формат «#,##0» для отображения чисел с разделителями тысяч.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Шаг 5: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

На этом реализация установки числового формата для оси с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для числового формата для оси с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Заключение

В этом руководстве вы узнали, как установить числовой формат для оси на диаграмме с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, вы можете создать новый документ, вставить столбчатую диаграмму, добавить ряд данных и отформатировать метки осей для отображения чисел в определенном формате.

Aspose.Words для .NET предоставляет мощные функции для настройки внешнего вида диаграмм в документах Word. Установив числовой формат для меток осей, вы можете контролировать способ отображения чисел, включая такие параметры, как десятичные разряды, разделители тысяч, символы валюты и многое другое. Это позволяет представлять числовые данные в ясной и понятной форме.

С Aspose.Words для .NET у вас есть возможность гибко форматировать различные аспекты диаграммы, включая метки осей. Установив числовой формат для оси, вы можете обеспечить согласованность и улучшить читаемость диаграммы, упростив пользователям интерпретацию представленных значений.

### Часто задаваемые вопросы

#### Q1. Каков числовой формат для оси на диаграмме?
Числовой формат для оси на диаграмме относится к форматированию, применяемому к числовым значениям, отображаемым на оси. Он позволяет вам контролировать способ представления чисел, включая такие параметры, как десятичные разряды, разделители тысяч, символы валюты, знаки процента и многое другое. Установив числовой формат, вы можете настроить внешний вид числовых данных на диаграмме в соответствии со своими конкретными требованиями.

#### Q2. Как я могу установить числовой формат для меток осей?
 Чтобы установить числовой формат для меток осей на диаграмме с помощью Aspose.Words for .NET, вы можете получить доступ к`AxisY` свойство диаграммы и установить`NumberFormat.FormatCode`в желаемый код формата. Код формата следует синтаксису стандартных шаблонов числового форматирования и определяет способ отображения чисел. Например, вы можете использовать "#,##0.00" для отображения чисел с двумя десятичными знаками и разделителями тысяч.

#### Q3. Можно ли установить разные числовые форматы для меток оси X и оси Y?
Да, вы можете установить разные числовые форматы для меток по осям X и Y, используя Aspose.Words для .NET. Доступ к соответствующей оси (`AxisX` для оси X или`AxisY` для оси Y) диаграммы и измените`NumberFormat.FormatCode` свойство индивидуально для каждой оси. Это позволяет применять различные числовые форматы к меткам на каждой оси в зависимости от ваших конкретных требований.

#### Q4. Какие коды распространенных форматов чисел я могу использовать?
Aspose.Words для .NET поддерживает широкий спектр кодов числовых форматов, которые можно использовать для форматирования меток осей на диаграмме. Некоторые распространенные коды формата включают:

- `0` или`#` - Отображает число без десятичных знаков.
- `0.00` или`#.00` - Отображает число с двумя десятичными знаками.
- `#,##0` Отображает число с разделителями тысяч.
- `"€"0.00` - Отображает число с символом валюты евро и двумя десятичными знаками.
- `"%"0` - Отображает число в процентах.

 Вы можете найти более подробную информацию о номере[коды форматов](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) в Справочнике по API Aspose.Words для .NET.

#### Q5. Могу ли я настроить другие свойства меток осей?
Да, Aspose.Words для .NET предоставляет широкий спектр свойств для настройки внешнего вида и поведения меток осей. В дополнение к числовому формату вы можете изменить такие свойства, как шрифт, размер, цвет, ориентация, выравнивание и многое другое. Это позволяет вам полностью настроить метки осей в соответствии с желаемым стилем и требованиями к презентации.