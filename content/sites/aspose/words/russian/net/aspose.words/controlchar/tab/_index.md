---
title: ControlChar.Tab
second_title: Справочник по API Aspose.Words для .NET
description: ControlChar поле. Символ табуляции x0009 или t.
type: docs
weight: 270
url: /ru/net/aspose.words/controlchar/tab/
---
## ControlChar.Tab field

Символ табуляции: "\x0009" или "\t".

```csharp
public static readonly string Tab;
```

### Примеры

Показывает, как установить собственный интервал для позиций табуляции.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Установите позиции табуляции так, чтобы они появлялись через каждые 72 пункта (1 дюйм).
builder.Document.DefaultTabStop = 72;

// Каждый символ табуляции привязывает текст после него к ближайшей позиции табуляции.
builder.Writeln("Hello" + ControlChar.Tab + "World!");
builder.Writeln("Hello" + ControlChar.TabChar + "World!");
```

### Смотрите также

* class [ControlChar](../)
* пространство имен [Aspose.Words](../../controlchar/)
* сборка [Aspose.Words](../../../)


