---
title: Class RevisionCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.RevisionCollection сорт. КоллекцияRevision объекты представляющие исправления в документе.
type: docs
weight: 4510
url: /ru/net/aspose.words/revisioncollection/
---
## RevisionCollection class

Коллекция[`Revision`](../revision/) объекты, представляющие исправления в документе.

```csharp
public class RevisionCollection : IEnumerable<Revision>
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words/revisioncollection/count/) { get; } | Возвращает количество ревизий в коллекции. |
| [Groups](../../aspose.words/revisioncollection/groups/) { get; } | Коллекция групп ревизий. |
| [Item](../../aspose.words/revisioncollection/item/) { get; } | Возвращает ревизию по указанному индексу. |

## Методы

| Имя | Описание |
| --- | --- |
| [AcceptAll](../../aspose.words/revisioncollection/acceptall/)() | Принимает все версии в этой коллекции. |
| [GetEnumerator](../../aspose.words/revisioncollection/getenumerator/)() | Возвращает объект перечислителя. |
| [RejectAll](../../aspose.words/revisioncollection/rejectall/)() | Отклоняет все версии в этой коллекции. |

### Примечания

Вы не создаете экземпляры этого класса напрямую. Использовать[`Revisions`](../document/revisions/) свойство, чтобы получить ревизии, присутствующие в документе.

### Примеры

Показывает, как работать с исправлениями в документе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Обычное редактирование документа не считается правкой.
builder.Write("This does not count as a revision. ");

Assert.IsFalse(doc.HasRevisions);

// Чтобы зарегистрировать наши правки как ревизии, нам нужно объявить автора, а затем начать их отслеживать.
doc.StartTrackRevisions("John Doe", DateTime.Now);

builder.Write("This is revision #1. ");

Assert.IsTrue(doc.HasRevisions);
Assert.AreEqual(1, doc.Revisions.Count);

// Этот флаг соответствует "Обзору" -> "Отслеживание" -> Опция «Отслеживать изменения» в Microsoft Word.
// Метод StartTrackRevisions не влияет на его значение,
// и документ отслеживает версии программно, несмотря на то, что имеет значение "false".
// Если мы откроем этот документ с помощью Microsoft Word, он не будет отслеживать редакции.
Assert.IsFalse(doc.TrackRevisions);

// Мы добавили текст с помощью конструктора документов, поэтому первая ревизия является ревизией типа вставки.
Revision revision = doc.Revisions[0];
Assert.AreEqual("John Doe", revision.Author);
Assert.AreEqual("This is revision #1. ", revision.ParentNode.GetText());
Assert.AreEqual(RevisionType.Insertion, revision.RevisionType);
Assert.AreEqual(revision.DateTime.Date, DateTime.Now.Date);
Assert.AreEqual(doc.Revisions.Groups[0], revision.Group);

// Удалить прогон, чтобы создать ревизию типа удаления.
doc.FirstSection.Body.FirstParagraph.Runs[0].Remove();

// Добавление новой ревизии помещает ее в начало коллекции ревизий.
Assert.AreEqual(RevisionType.Deletion, doc.Revisions[0].RevisionType);
Assert.AreEqual(2, doc.Revisions.Count);

// Вставляемые ревизии отображаются в теле документа даже до того, как мы принимаем/отклоняем ревизию.
// Отклонение ревизии удалит ее узлы из тела. И наоборот, узлы, из которых состоят ревизии удаления
// также задерживаемся в документе, пока не примем исправление.
Assert.AreEqual("This does not count as a revision. This is revision #1.", doc.GetText().Trim());

// Принятие удаления ревизии удалит ее родительский узел из текста абзаца
// а затем удалить саму ревизию коллекции.
doc.Revisions[0].Accept();

Assert.AreEqual(1, doc.Revisions.Count);
Assert.AreEqual("This is revision #1.", doc.GetText().Trim());

builder.Writeln("");
builder.Write("This is revision #2.");

// Теперь переместите узел, чтобы создать перемещаемый тип ревизии.
Node node = doc.FirstSection.Body.Paragraphs[1];
Node endNode = doc.FirstSection.Body.Paragraphs[1].NextSibling;
Node referenceNode = doc.FirstSection.Body.Paragraphs[0];

while (node != endNode)
{
    Node nextNode = node.NextSibling;
    doc.FirstSection.Body.InsertBefore(node, referenceNode);
    node = nextNode;
}

Assert.AreEqual(RevisionType.Moving, doc.Revisions[0].RevisionType);
Assert.AreEqual(8, doc.Revisions.Count);
Assert.AreEqual("This is revision #2.\rThis is revision #1. \rThis is revision #2.", doc.GetText().Trim());

// Перемещаемая ревизия теперь имеет индекс 1. Отклоните ревизию, чтобы удалить ее содержимое.
doc.Revisions[1].Reject();

Assert.AreEqual(6, doc.Revisions.Count);
Assert.AreEqual("This is revision #1. \rThis is revision #2.", doc.GetText().Trim());
```

### Смотрите также

* class [Revision](../revision/)
* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


