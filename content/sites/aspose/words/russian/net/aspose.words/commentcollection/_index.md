---
title: Class CommentCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.CommentCollection сорт. Предоставляет типизированный доступ к коллекцииComment узлы.
type: docs
weight: 230
url: /ru/net/aspose.words/commentcollection/
---
## CommentCollection class

Предоставляет типизированный доступ к коллекции[`Comment`](../comment/) узлы.

```csharp
public class CommentCollection : NodeCollection
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Получает количество узлов в коллекции. |
| [Item](../../aspose.words/commentcollection/item/) { get; } | Получает **Комментарий** по данному индексу. (2 indexers) |

## Методы

| Имя | Описание |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Добавляет узел в конец коллекции. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Удаляет все узлы из этой коллекции и из документа. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Определяет, находится ли узел в коллекции. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Обеспечивает простую итерацию в стиле foreach по набору узлов. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Возвращает отсчитываемый от нуля индекс указанного узла. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Вставляет узел в коллекцию по указанному индексу. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Удаляет узел из коллекции и из документа. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Удаляет узел с указанным индексом из коллекции и из документа. |
| [ToArray](../../aspose.words/nodecollection/toarray/)() | Копирует все узлы из коллекции в новый массив узлов. |

### Примеры

Показывает, как пометить комментарий как «готовый».

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Helo world!");

// Вставляем комментарий, чтобы указать на ошибку. 
Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("Fix the spelling error!");
doc.FirstSection.Body.FirstParagraph.AppendChild(comment);

// Комментарии имеют флаг «Готово», который по умолчанию установлен на «ложь». 
// Если в комментарии предлагается внести изменения в документ,
// мы можем применить изменение, а затем также установить флаг «Готово», чтобы указать на исправление.
Assert.False(comment.Done);

doc.FirstSection.Body.FirstParagraph.Runs[0].Text = "Hello world!";
comment.Done = true;

// Комментарии, которые «готовы», будут отличаться друг от друга
// из тех, которые не "готовы" с блеклым цветом текста.
comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("Add text to this paragraph.");
builder.CurrentParagraph.AppendChild(comment);

doc.Save(ArtifactsDir + "Comment.Done.docx");
```

### Смотрите также

* class [NodeCollection](../nodecollection/)
* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


