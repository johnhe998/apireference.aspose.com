---
title: Table.PreferredWidth
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Получает или задает предпочтительную ширину таблицы.
type: docs
weight: 220
url: /ru/net/aspose.words.tables/table/preferredwidth/
---
## Table.PreferredWidth property

Получает или задает предпочтительную ширину таблицы.

```csharp
public PreferredWidth PreferredWidth { get; set; }
```

### Примечания

Значение по умолчанию[`Auto`](../../preferredwidth/auto/).

### Примеры

Показывает, как настроить таблицу так, чтобы она автоматически подгонялась под 50 % ширины страницы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell #1");
builder.InsertCell();
builder.Write("Cell #2");
builder.InsertCell();
builder.Write("Cell #3");

table.PreferredWidth = PreferredWidth.FromPercent(50);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithPreferredWidth.docx");
```

### Смотрите также

* class [PreferredWidth](../../preferredwidth/)
* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


