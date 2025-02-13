---
title: Document.UpdateWordCount
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Обновляет свойства количества слов в документе.
type: docs
weight: 770
url: /ru/net/aspose.words/document/updatewordcount/
---
## UpdateWordCount() {#updatewordcount}

Обновляет свойства количества слов в документе.

```csharp
public void UpdateWordCount()
```

### Примечания

**Упдейвордкаунт** пересчитывает и обновляет свойства символов, слов и абзацев в[`BuiltInDocumentProperties`](../builtindocumentproperties/) коллекция **Документ**.

Обратите внимание, что **Упдейвордкаунт** не обновляет количество строк и свойства страниц. Используйте`UpdateWordCount` перегрузите и передайте значение True в качестве параметра для этого.

Когда вы используете ознакомительную версию, водяной знак ознакомительной версии также будет включен в количество слов.

### Примеры

Показывает, как обновить все метки списков в документе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("Ut enim ad minim veniam, " +
                "quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Aspose.Words не отслеживает подобные показатели документов в режиме реального времени.
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Paragraphs);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

// Чтобы получить точные значения для трех из этих свойств, нам нужно будет обновить их вручную.
doc.UpdateWordCount();

Assert.AreEqual(196, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(36, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(2, doc.BuiltInDocumentProperties.Paragraphs);

// Для подсчета строк нам потребуется вызвать специальную перегрузку метода обновления.
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

doc.UpdateWordCount(true);

Assert.AreEqual(4, doc.BuiltInDocumentProperties.Lines);
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)

---

## UpdateWordCount(bool) {#updatewordcount_1}

Обновляет свойства количества слов в документе, опционально обновляет[`Lines`](../../../aspose.words.properties/builtindocumentproperties/lines/) свойство.

```csharp
public void UpdateWordCount(bool updateLinesCount)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| updateLinesCount | Boolean | Истинно, если количество строк в документе должно быть рассчитано. |

### Примечания

Этот метод перестроит макет страницы документа.

### Примеры

Показывает, как обновить все метки списков в документе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("Ut enim ad minim veniam, " +
                "quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Aspose.Words не отслеживает подобные показатели документов в режиме реального времени.
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Paragraphs);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

// Чтобы получить точные значения для трех из этих свойств, нам нужно будет обновить их вручную.
doc.UpdateWordCount();

Assert.AreEqual(196, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(36, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(2, doc.BuiltInDocumentProperties.Paragraphs);

// Для подсчета строк нам потребуется вызвать специальную перегрузку метода обновления.
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

doc.UpdateWordCount(true);

Assert.AreEqual(4, doc.BuiltInDocumentProperties.Lines);
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


