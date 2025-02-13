---
title: Получить межстрочный интервал шрифта
linktitle: Получить межстрочный интервал шрифта
second_title: API обработки документов Aspose.Words
description: Из этого руководства вы узнаете, как получить межстрочный интервал шрифта в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/get-font-line-spacing/
---
В этом уроке мы расскажем вам, как получить межстрочный интервал шрифта в документе Word, используя библиотеку Aspose.Words для .NET. Межстрочный интервал шрифта определяет вертикальное расстояние между строками текста. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Создайте новый документ и генератор документов
 Во-первых, мы создадим новый документ, создав экземпляр`Document` класс и конструктор документов, создав экземпляр`DocumentBuilder` сорт.

```csharp
// Создать новый документ
Document doc = new Document();

//Создать генератор документов
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Настройте шрифт
 Далее мы настроим шрифт, установив`Name` свойство генератора документов.

```csharp
// Настроить шрифт
builder.Font.Name = "Calibri";
```

## Шаг 3: Добавьте текст в документ
Теперь мы будем использовать генератор документов, чтобы добавить форматированный текст в документ.

```csharp
// Добавить текст в документ
builder. Writen("qText");
```

## Шаг 4: Получите межстрочный интервал шрифта
 Теперь мы получим доступ к`Font` объекта первого абзаца документа и получить значение`LineSpacing` свойство.

```csharp
// Получить межстрочный интервал шрифта
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Пример исходного кода для получения межстрочного интервала шрифта с использованием Aspose.Words для .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Заключение
В этом руководстве мы увидели, как получить межстрочный интервал шрифта в документе Word с помощью Aspose.Words для .NET. Межстрочный интервал шрифта важен для управления вертикальным интервалом между строками текста. Не стесняйтесь использовать эту функцию, чтобы настроить внешний вид вашего текста в ваших документах.

### Часто задаваемые вопросы

#### В: Как изменить межстрочный интервал определенного текста в документе Word?

О: С помощью Aspose.Words вы можете легко изменить межстрочный интервал определенного текста в документе Word. Используйте API, чтобы выбрать нужный текст и отрегулировать расстояние между строками, указав соответствующее значение.

#### В: Можно ли применить точное расстояние между строками в документе Word?

О: Да, Aspose.Words позволяет вам применять точные интервалы между строками в документе Word. Вы можете указать точное значение межстрочного интервала с помощью API.

#### В: Как настроить межстрочный интервал для всего документа Word?

О: С помощью Aspose.Words вы можете легко настроить межстрочный интервал для всего документа Word. Используйте методы, предоставляемые API, чтобы указать желаемый межстрочный интервал для всего документа.

#### В: Поддерживает ли Aspose.Words несколько межстрочных интервалов?

О: Да, Aspose.Words поддерживает несколько межстрочных интервалов в документах Word. Вы можете установить несколько интервалов, например, 1,5-кратный или 2-кратный нормальный интервал для строк вашего текста.

#### Вопрос. Как избежать проблем с перекрытием строк при настройке межстрочного интервала?

О: Чтобы избежать проблем с перекрытием строк при настройке интервала между строками, обязательно выберите соответствующие значения интервала. Также проверьте окончательный рендеринг вашего документа, чтобы убедиться, что текст остается читаемым и хорошо отформатирован.