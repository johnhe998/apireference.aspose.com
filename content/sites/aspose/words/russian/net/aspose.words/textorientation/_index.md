---
title: Enum TextOrientation
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.TextOrientation перечисление. Задает ориентацию текста на странице в ячейке таблицы или текстовом фрейме.
type: docs
weight: 6130
url: /ru/net/aspose.words/textorientation/
---
## TextOrientation enumeration

Задает ориентацию текста на странице, в ячейке таблицы или текстовом фрейме.

```csharp
public enum TextOrientation
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Horizontal | `0` | Текст расположен горизонтально (lr-tb). |
| Downward | `1` | Текст повернут на 90 градусов вправо, чтобы он отображался сверху вниз (tb-rl). |
| Upward | `3` | Текст повернут на 90 градусов влево и отображается снизу вверх (bt-lr). |
| HorizontalRotatedFarEast | `4` | Текст расположен горизонтально, но дальневосточные символы повернуты на 90 градусов влево (lr-tb-v). |
| VerticalFarEast | `5` | Дальневосточные символы отображаются вертикально, остальной текст поворачивается на 90 градусов вправо, чтобы отображаться сверху вниз (tb-rl-v). |
| VerticalRotatedFarEast | `7` | Дальневосточные символы отображаются вертикально, остальной текст поворачивается на 90 градусов вправо, чтобы отображаться сверху вниз по вертикали, а затем слева направо по горизонтали (tb-lr-v). |

### Примеры

Показывает, как построить отформатированную таблицу 2x2.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndRow();

// При построении таблицы построитель документов применит текущие значения свойств RowFormat/CellFormat
// к текущей строке/ячейке, в которой находится его курсор, и к любым новым строкам/ячейкам по мере их создания.
Assert.AreEqual(CellVerticalAlignment.Center, table.Rows[0].Cells[0].CellFormat.VerticalAlignment);
Assert.AreEqual(CellVerticalAlignment.Center, table.Rows[0].Cells[1].CellFormat.VerticalAlignment);

builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Write("Row 2, cell 1.");
builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Write("Row 2, cell 2.");
builder.EndRow();
builder.EndTable();

// На ранее добавленные строки и ячейки изменения форматирования построителя не влияют задним числом.
Assert.AreEqual(0, table.Rows[0].RowFormat.Height);
Assert.AreEqual(HeightRule.Auto, table.Rows[0].RowFormat.HeightRule);
Assert.AreEqual(100, table.Rows[1].RowFormat.Height);
Assert.AreEqual(HeightRule.Exactly, table.Rows[1].RowFormat.HeightRule);
Assert.AreEqual(TextOrientation.Upward, table.Rows[1].Cells[0].CellFormat.Orientation);
Assert.AreEqual(TextOrientation.Downward, table.Rows[1].Cells[1].CellFormat.Orientation);

doc.Save(ArtifactsDir + "DocumentBuilder.BuildTable.docx");
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


