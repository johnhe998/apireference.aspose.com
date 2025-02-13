---
title: LayoutOptions.ShowParagraphMarks
second_title: Справочник по API Aspose.Words для .NET
description: LayoutOptions свойство. Получает или задает индикацию того отображаются ли знаки абзаца. Значение по умолчанию  False.
type: docs
weight: 80
url: /ru/net/aspose.words.layout/layoutoptions/showparagraphmarks/
---
## LayoutOptions.ShowParagraphMarks property

Получает или задает индикацию того, отображаются ли знаки абзаца. Значение по умолчанию — False.

```csharp
public bool ShowParagraphMarks { get; set; }
```

### Примеры

Показывает, как отображать метки абзаца в визуализируемом выходном документе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Добавьте несколько абзацев, затем включите метки абзаца, чтобы показать концы абзацев
// с символом пилкроу (¶) при отображении документа.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

doc.LayoutOptions.ShowParagraphMarks = showParagraphMarks;

doc.Save(ArtifactsDir + "Document.LayoutOptionsParagraphMarks.pdf");
```

### Смотрите также

* class [LayoutOptions](../)
* пространство имен [Aspose.Words.Layout](../../layoutoptions/)
* сборка [Aspose.Words](../../../)


