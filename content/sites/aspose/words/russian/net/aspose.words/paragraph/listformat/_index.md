---
title: Paragraph.ListFormat
second_title: Справочник по API Aspose.Words для .NET
description: Paragraph свойство. Предоставляет доступ к свойствам форматирования списка абзаца.
type: docs
weight: 150
url: /ru/net/aspose.words/paragraph/listformat/
---
## Paragraph.ListFormat property

Предоставляет доступ к свойствам форматирования списка абзаца.

```csharp
public ListFormat ListFormat { get; }
```

### Примеры

Показывает, как вывести все абзацы в документе, которые являются элементами списка.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Numbered list item 1");
builder.Writeln("Numbered list item 2");
builder.Writeln("Numbered list item 3");
builder.ListFormat.RemoveNumbers();

builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Bulleted list item 1");
builder.Writeln("Bulleted list item 2");
builder.Writeln("Bulleted list item 3");
builder.ListFormat.RemoveNumbers();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{ 
    Console.WriteLine($"This paragraph belongs to list ID# {para.ListFormat.List.ListId}, number style \"{para.ListFormat.ListLevel.NumberStyle}\"");
    Console.WriteLine($"\t\"{para.GetText().Trim()}\"");
}
```

### Смотрите также

* class [ListFormat](../../../aspose.words.lists/listformat/)
* class [Paragraph](../)
* пространство имен [Aspose.Words](../../paragraph/)
* сборка [Aspose.Words](../../../)


