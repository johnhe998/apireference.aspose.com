---
title: FindReplaceOptions.IgnoreDeleted
second_title: Справочник по API Aspose.Words для .NET
description: FindReplaceOptions свойство. Получает или задает логическое значение указывающее следует ли игнорировать текст внутри удаленных ревизий. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 60
url: /ru/net/aspose.words.replacing/findreplaceoptions/ignoredeleted/
---
## FindReplaceOptions.IgnoreDeleted property

Получает или задает логическое значение, указывающее, следует ли игнорировать текст внутри удаленных ревизий. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool IgnoreDeleted { get; set; }
```

### Примеры

Показывает, как включать или игнорировать текст внутри удаляемых редакций во время операции поиска и замены.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

// Запускаем отслеживание ревизий и удаляем второй абзац, что приведет к удалению ревизии.
// Этот абзац останется в документе до тех пор, пока мы не примем удаление редакции.
doc.StartTrackRevisions("John Doe", DateTime.Now);
doc.FirstSection.Body.Paragraphs[1].Remove();
doc.StopTrackRevisions();

Assert.True(doc.FirstSection.Body.Paragraphs[1].IsDeleteRevision);

// Мы можем использовать объект «FindReplaceOptions», чтобы изменить процесс поиска и замены.
FindReplaceOptions options = new FindReplaceOptions();

// Установите для флага «IgnoreDeleted» значение «true», чтобы получить функцию поиска и замены
// операция для игнорирования абзацев, которые удаляют ревизии.
// Установите для флага «IgnoreDeleted» значение «false», чтобы получить функцию поиска и замены
// операция также для поиска текста внутри редакций удаления.
options.IgnoreDeleted = ignoreTextInsideDeleteRevisions;

doc.Range.Replace("Hello", "Greetings", options);

Assert.AreEqual(
    ignoreTextInsideDeleteRevisions
        ? "Greetings world!\rHello again!"
        : "Greetings world!\rGreetings again!", doc.GetText().Trim());
```

### Смотрите также

* class [FindReplaceOptions](../)
* пространство имен [Aspose.Words.Replacing](../../findreplaceoptions/)
* сборка [Aspose.Words](../../../)


