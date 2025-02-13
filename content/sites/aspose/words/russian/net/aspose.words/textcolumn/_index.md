---
title: Class TextColumn
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.TextColumn сорт. Представляет один текстовый столбец. Текстовая колонка является членомTextColumnCollection коллекция.  Текстовые столбцы коллекция включает все столбцы в разделе документа.
type: docs
weight: 6090
url: /ru/net/aspose.words/textcolumn/
---
## TextColumn class

Представляет один текстовый столбец. **Текстовая колонка** является членом[`TextColumnCollection`](../textcolumncollection/) коллекция.  **Текстовые столбцы** коллекция включает все столбцы в разделе документа.

```csharp
public class TextColumn
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [SpaceAfter](../../aspose.words/textcolumn/spaceafter/) { get; set; } | Получает или задает расстояние между этим столбцом и следующим столбцом в пунктах. Не требуется для последнего столбца. |
| [Width](../../aspose.words/textcolumn/width/) { get; set; } | Получает или задает ширину текстового столбца в пунктах. |

### Примечания

**Текстовая колонка** объекты используются только для указания столбцов с пользовательской шириной и интервалом. Если вы хотите, чтобы столбцы в документе имели одинаковую ширину, установите TextColumns.[`EvenlySpaced`](../textcolumncollection/evenlyspaced/) к **истинный**.

Когда новый **Текстовая колонка** создается, его ширина и интервал равны нулю.

### Примеры

Показывает, как создавать неравномерно расположенные столбцы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
PageSetup pageSetup = builder.PageSetup;

TextColumnCollection columns = pageSetup.TextColumns;
columns.EvenlySpaced = false;
columns.SetCount(2);

// Определяем количество места, которое у нас есть для размещения столбцов.
double contentWidth = pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin;

Assert.AreEqual(470.30d, contentWidth, 0.01d);

// Сделать первый столбец узким.
TextColumn column = columns[0];
column.Width = 100;
column.SpaceAfter = 20;

// Устанавливаем второй столбец так, чтобы он занимал оставшееся пространство, доступное на полях страницы.
column = columns[1];
column.Width = contentWidth - column.Width - column.SpaceAfter;

builder.Writeln("Narrow column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Wide column 2.");

doc.Save(ArtifactsDir + "PageSetup.CustomColumnWidth.docx");
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


