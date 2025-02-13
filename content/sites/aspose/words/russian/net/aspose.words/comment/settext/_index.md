---
title: Comment.SetText
second_title: Справочник по API Aspose.Words для .NET
description: Comment метод. Это удобный метод позволяющий легко задать текст комментария.
type: docs
weight: 150
url: /ru/net/aspose.words/comment/settext/
---
## Comment.SetText method

Это удобный метод, позволяющий легко задать текст комментария.

```csharp
public void SetText(string text)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| text | String | Новый текст комментария. |

### Примечания

Этот метод позволяет быстро задать текст комментария из строки. Строка может содержать разрывы абзацев, это соответственно создаст абзацы текста в комментарии. Если вы хотите вставить в комментарий более сложные элементы, например закладки или таблицы или применить расширенное форматирование, то вам нужно использовать соответствующие классы узлов на создайте текст комментария.

### Примеры

Показывает, как добавить комментарий к документу, а затем ответить на него.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

// Разместите комментарий в узле в теле документа.
// Этот комментарий будет отображаться в месте своего абзаца,
// за пределами правого поля страницы и с пунктирной линией, соединяющей его с абзацем.
builder.CurrentParagraph.AppendChild(comment);

// Добавляем ответ, который будет отображаться под родительским комментарием.
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");

// Комментарии и ответы являются узлами комментариев.
Assert.AreEqual(2, doc.GetChildNodes(NodeType.Comment, true).Count);

// Комментарии, которые не отвечают на другие комментарии, относятся к "верхнему уровню". У них нет комментариев предков.
Assert.Null(comment.Ancestor);

// Ответы имеют родительский комментарий верхнего уровня.
Assert.AreEqual(comment, comment.Replies[0].Ancestor);

doc.Save(ArtifactsDir + "Comment.AddCommentWithReply.docx");
```

### Смотрите также

* class [Comment](../)
* пространство имен [Aspose.Words](../../comment/)
* сборка [Aspose.Words](../../../)


