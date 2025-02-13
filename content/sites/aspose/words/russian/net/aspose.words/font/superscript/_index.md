---
title: Font.Superscript
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Истинно если шрифт отформатирован как надстрочный.
type: docs
weight: 440
url: /ru/net/aspose.words/font/superscript/
---
## Font.Superscript property

Истинно, если шрифт отформатирован как надстрочный.

```csharp
public bool Superscript { get; set; }
```

### Примеры

Показывает, как форматировать текст, чтобы сместить его положение.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

// Поднимите этот фрагмент текста на 5 пунктов выше базовой линии.
Run run = new Run(doc, "Raised text. ");
run.Font.Position = 5;
para.AppendChild(run);

// Опустите этот фрагмент текста на 10 пунктов ниже базовой линии.
run = new Run(doc, "Lowered text. ");
run.Font.Position = -10;
para.AppendChild(run);

// Добавляем ряд обычного текста.
run = new Run(doc, "Text in its default position. ");
para.AppendChild(run);

// Добавляем фрагмент текста, который отображается как нижний индекс.
run = new Run(doc, "Subscript. ");
run.Font.Subscript = true;
para.AppendChild(run);

// Добавляем фрагмент текста, который отображается как верхний индекс.
run = new Run(doc, "Superscript.");
run.Font.Superscript = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.PositionSubscript.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


