---
title: Comment.StoryType
second_title: Справочник по API Aspose.Words для .NET
description: Comment свойство. Возвращает StoryType.Comments .
type: docs
weight: 100
url: /ru/net/aspose.words/comment/storytype/
---
## Comment.StoryType property

Возвращает **StoryType.Comments** .

```csharp
public override StoryType StoryType { get; }
```

### Примеры

Показывает, как вставлять узлы InlineStory.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, null);

// Узлы таблицы имеют метод "EnsureMinimum()", который проверяет, есть ли в таблице хотя бы одна ячейка.
Table table = new Table(doc);
table.EnsureMinimum();

// Мы можем разместить таблицу внутри сноски, чтобы она отображалась в нижнем колонтитуле ссылающейся страницы.
Assert.That(footnote.Tables, Is.Empty);
footnote.AppendChild(table);
Assert.AreEqual(1, footnote.Tables.Count);
Assert.AreEqual(NodeType.Table, footnote.LastChild.NodeType);

// InlineStory также имеет метод "EnsureMinimum()", но в этом случае
// это гарантирует, что последним дочерним элементом узла будет абзац,
// чтобы мы могли легко нажимать и писать текст в Microsoft Word.
footnote.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, footnote.LastChild.NodeType);

// Редактируем внешний вид якоря, который представляет собой маленькое число в верхнем индексе
// в основном тексте, который указывает на сноску.
footnote.Font.Name = "Arial";
footnote.Font.Color = Color.Green;

// Все встроенные узлы истории имеют соответствующие типы историй.
Assert.AreEqual(StoryType.Footnotes, footnote.StoryType);

// Комментарий — это еще один тип встроенной истории.
Comment comment = (Comment)builder.CurrentParagraph.AppendChild(new Comment(doc, "John Doe", "J. D.", DateTime.Now));

// Родительский абзац встроенного узла истории будет абзацем основного тела документа.
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, comment.ParentParagraph);

// Тем не менее, последний абзац — это текст содержимого комментария,
// который будет находиться за пределами основного тела документа во всплывающей подсказке.
// Комментарий по умолчанию не будет иметь дочерних узлов,
// поэтому мы можем применить метод ГарантиМинимум(), чтобы поместить здесь абзац.
Assert.Null(comment.LastParagraph);
comment.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, comment.LastChild.NodeType);

// Когда у нас есть абзац, мы можем переместить конструктор, чтобы он сделал это, и написать наш комментарий.
builder.MoveTo(comment.LastParagraph);
builder.Write("My comment.");

Assert.AreEqual(StoryType.Comments, comment.StoryType);

doc.Save(ArtifactsDir + "InlineStory.InsertInlineStoryNodes.docx");
```

### Смотрите также

* enum [StoryType](../../storytype/)
* class [Comment](../)
* пространство имен [Aspose.Words](../../comment/)
* сборка [Aspose.Words](../../../)


