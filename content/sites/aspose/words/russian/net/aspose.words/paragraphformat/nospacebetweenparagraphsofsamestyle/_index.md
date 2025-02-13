---
title: ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Если верноSpaceBefore а такжеSpaceAfter будет игнорироваться между абзацами одного стиля.
type: docs
weight: 230
url: /ru/net/aspose.words/paragraphformat/nospacebetweenparagraphsofsamestyle/
---
## ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle property

Если верно,[`SpaceBefore`](../spacebefore/) а также[`SpaceAfter`](../spaceafter/) будет игнорироваться между абзацами одного стиля.

```csharp
public bool NoSpaceBetweenParagraphsOfSameStyle { get; set; }
```

### Примечания

Этот параметр действует только при применении к стилю абзаца. Если применить к абзацу напрямую, это не имеет никакого эффекта.

### Примеры

Показывает, как применить без интервала между абзацами в одном стиле.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Применить большое количество интервалов до и после абзацев, которые создаст этот конструктор.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Установите для флага "NoSpaceBetweenParagraphsOfSameStyle" значение "true" для применения
// без интервала между абзацами с одинаковым стилем, который будет группировать похожие абзацы.
// Оставляем флаг "NoSpaceBetweenParagraphsOfSameStyle" как "false"
// для равномерного применения интервалов к каждому абзацу.
builder.ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle = noSpaceBetweenParagraphsOfSameStyle;

builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingSameStyle.docx");
```

### Смотрите также

* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


