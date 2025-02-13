---
title: ParagraphFormat.LineSpacingRule
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Получает или задает межстрочный интервал для абзаца.
type: docs
weight: 190
url: /ru/net/aspose.words/paragraphformat/linespacingrule/
---
## ParagraphFormat.LineSpacingRule property

Получает или задает межстрочный интервал для абзаца.

```csharp
public LineSpacingRule LineSpacingRule { get; set; }
```

### Примеры

Показывает, как работать с межстрочным интервалом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ниже приведены три правила межстрочного интервала, которые мы можем определить с помощью
// свойство абзаца "LineSpacingRule" для настройки интервала между абзацами.
// 1 - Установить минимальное расстояние.
// Это даст вертикальный отступ для строк текста любого размера
// это слишком мало, чтобы поддерживать минимальную высоту строки.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.AtLeast;
builder.ParagraphFormat.LineSpacing = 20;

builder.Writeln("Minimum line spacing of 20.");
builder.Writeln("Minimum line spacing of 20.");

// 2 - Установить точный интервал.
// Использование размеров шрифта, которые слишком велики для интервала, приведет к обрезанию текста.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Exactly;
builder.ParagraphFormat.LineSpacing = 5;

builder.Writeln("Line spacing of exactly 5.");
builder.Writeln("Line spacing of exactly 5.");

// 3 - Установите интервал как кратный межстрочному интервалу по умолчанию, который по умолчанию составляет 12 пунктов.
// Этот тип интервала будет масштабироваться для разных размеров шрифта.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Multiple;
builder.ParagraphFormat.LineSpacing = 18;

builder.Writeln("Line spacing of 1.5 default lines.");
builder.Writeln("Line spacing of 1.5 default lines.");

doc.Save(ArtifactsDir + "ParagraphFormat.LineSpacing.docx");
```

### Смотрите также

* enum [LineSpacingRule](../../linespacingrule/)
* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


