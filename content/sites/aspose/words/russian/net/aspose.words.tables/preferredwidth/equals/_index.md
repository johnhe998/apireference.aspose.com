---
title: PreferredWidth.Equals
second_title: Справочник по API Aspose.Words для .NET
description: PreferredWidth метод. Определяет равна ли указанная PreferredWidth по значению текущей PreferredWidth.
type: docs
weight: 60
url: /ru/net/aspose.words.tables/preferredwidth/equals/
---
## Equals(PreferredWidth) {#equals}

Определяет, равна ли указанная PreferredWidth по значению текущей PreferredWidth.

```csharp
public bool Equals(PreferredWidth other)
```

### Примеры

Показывает, как установить предпочтительную ширину для ячеек таблицы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Существует два способа применения класса PreferredWidth к ячейкам таблицы.
// 1 - Установить абсолютную предпочтительную ширину в пунктах:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - Установите относительную предпочтительную ширину в процентах от ширины таблицы:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// Ячейка, для которой не указана предпочтительная ширина, займет оставшееся доступное пространство.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// Каждая конфигурация свойства PreferredWidth создает новый объект.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### Смотрите также

* class [PreferredWidth](../)
* пространство имен [Aspose.Words.Tables](../../preferredwidth/)
* сборка [Aspose.Words](../../../)

---

## Equals(object) {#equals_1}

Определяет, равен ли указанный объект по значению текущему объекту.

```csharp
public override bool Equals(object obj)
```

### Примеры

Показывает, как установить предпочтительную ширину для ячеек таблицы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Существует два способа применения класса PreferredWidth к ячейкам таблицы.
// 1 - Установить абсолютную предпочтительную ширину в пунктах:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - Установите относительную предпочтительную ширину в процентах от ширины таблицы:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// Ячейка, для которой не указана предпочтительная ширина, займет оставшееся доступное пространство.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// Каждая конфигурация свойства PreferredWidth создает новый объект.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### Смотрите также

* class [PreferredWidth](../)
* пространство имен [Aspose.Words.Tables](../../preferredwidth/)
* сборка [Aspose.Words](../../../)


