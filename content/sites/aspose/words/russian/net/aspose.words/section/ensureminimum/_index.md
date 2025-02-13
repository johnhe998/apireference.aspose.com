---
title: Section.EnsureMinimum
second_title: Справочник по API Aspose.Words для .NET
description: Section метод. Гарантирует что раздел имеет тело с одним абзацем.
type: docs
weight: 130
url: /ru/net/aspose.words/section/ensureminimum/
---
## Section.EnsureMinimum method

Гарантирует, что раздел имеет тело с одним абзацем.

```csharp
public void EnsureMinimum()
```

### Примеры

Показывает, как подготовить новый узел раздела к редактированию.

```csharp
Document doc = new Document();

// Пустой документ состоит из раздела, в котором есть тело, а в нем, в свою очередь, есть абзац.
// Мы можем добавить содержимое в этот документ, добавив в этот абзац такие элементы, как текстовые фрагменты, фигуры или таблицы.
Assert.AreEqual(NodeType.Section, doc.GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Body, doc.Sections[0].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[0].Body.GetChild(NodeType.Any, 0, true).NodeType);

// Если мы добавим новый раздел, подобный этому, у него не будет ни тела, ни каких-либо других дочерних узлов.
doc.Sections.Add(new Section(doc));

Assert.AreEqual(0, doc.Sections[1].GetChildNodes(NodeType.Any, true).Count);

// Запустите метод "EnsureMinimum", чтобы добавить текст и абзац в этот раздел, чтобы начать его редактирование.
doc.LastSection.EnsureMinimum();

Assert.AreEqual(NodeType.Body, doc.Sections[1].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[1].Body.GetChild(NodeType.Any, 0, true).NodeType);

doc.Sections[0].Body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Смотрите также

* class [Section](../)
* пространство имен [Aspose.Words](../../section/)
* сборка [Aspose.Words](../../../)


