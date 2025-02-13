---
title: PageSetup.LineNumberCountBy
second_title: Справочник по API Aspose.Words для .NET
description: PageSetup свойство. Возвращает или задает числовое приращение для номеров строк.
type: docs
weight: 210
url: /ru/net/aspose.words/pagesetup/linenumbercountby/
---
## PageSetup.LineNumberCountBy property

Возвращает или задает числовое приращение для номеров строк.

```csharp
public int LineNumberCountBy { get; set; }
```

### Примеры

Показывает, как включить нумерацию строк для раздела.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Мы можем использовать объект раздела PageSetup для отображения чисел слева от текстовых строк раздела.
// Это то же поведение, что и у объекта List,
// но он охватывает весь раздел и никак не изменяет текст.
// Наш раздел будет перезапускать нумерацию на каждой новой странице с 1 и отображать номер,
// если кратно 3, на 50pt слева от строки.
PageSetup pageSetup = builder.PageSetup;
pageSetup.LineStartingNumber = 1;
pageSetup.LineNumberCountBy = 3;
pageSetup.LineNumberRestartMode = LineNumberRestartMode.RestartPage;
pageSetup.LineNumberDistanceFromText = 50.0d;

for (int i = 1; i <= 25; i++)
    builder.Writeln($"Line {i}.");

// Счетчик строк пропустит любой абзац с флагом "SuppressLineNumbers", установленным в "true".
// Этот абзац находится на 15-й строке, что кратно 3, поэтому обычно отображается номер строки.
// Счетчик строк секции также будет игнорировать эту строку, считая следующую строку 15-й,
// и продолжаем считать с этого момента.
doc.FirstSection.Body.Paragraphs[14].ParagraphFormat.SuppressLineNumbers = true;

doc.Save(ArtifactsDir + "PageSetup.LineNumbers.docx");
```

### Смотрите также

* class [PageSetup](../)
* пространство имен [Aspose.Words](../../pagesetup/)
* сборка [Aspose.Words](../../../)


