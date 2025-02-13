---
title: ControlChar.Cr
second_title: Справочник по API Aspose.Words для .NET
description: ControlChar поле. Символ возврата каретки x000d или r. Такой же какParagraphBreak .
type: docs
weight: 50
url: /ru/net/aspose.words/controlchar/cr/
---
## ControlChar.Cr field

Символ возврата каретки: "\x000d" или "\r". Такой же как[`ParagraphBreak`](../paragraphbreak/) .

```csharp
public static readonly string Cr;
```

### Примеры

Показывает, как использовать управляющие символы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем абзацы с текстом с помощью DocumentBuilder.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

// Преобразование документа в текстовую форму показывает, что управляющие символы
// представляют некоторые структурные элементы документа, такие как разрывы страниц.
Assert.AreEqual($"Hello world!{ControlChar.Cr}" +
                $"Hello again!{ControlChar.Cr}" +
                ControlChar.PageBreak, doc.GetText());

// При преобразовании документа в строковую форму
// мы можем опустить некоторые управляющие символы с помощью метода Trim.
Assert.AreEqual($"Hello world!{ControlChar.Cr}" +
                "Hello again!", doc.GetText().Trim());
```

### Смотрите также

* class [ControlChar](../)
* пространство имен [Aspose.Words](../../controlchar/)
* сборка [Aspose.Words](../../../)


