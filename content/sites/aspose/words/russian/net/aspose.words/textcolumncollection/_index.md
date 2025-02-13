---
title: Class TextColumnCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.TextColumnCollection сорт. КоллекцияTextColumn объекты представляющие все столбцы текста в разделе документа.
type: docs
weight: 6100
url: /ru/net/aspose.words/textcolumncollection/
---
## TextColumnCollection class

Коллекция[`TextColumn`](../textcolumn/) объекты, представляющие все столбцы текста в разделе документа.

```csharp
public class TextColumnCollection
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words/textcolumncollection/count/) { get; } | Получает количество столбцов в разделе документа. |
| [EvenlySpaced](../../aspose.words/textcolumncollection/evenlyspaced/) { get; set; } | **Истинный** если текстовые столбцы имеют одинаковую ширину и равномерно распределены. |
| [Item](../../aspose.words/textcolumncollection/item/) { get; } | Возвращает текстовый столбец по указанному индексу. |
| [LineBetween](../../aspose.words/textcolumncollection/linebetween/) { get; set; } | Когда **истинный** , добавляет вертикальную линию между столбцами. |
| [Spacing](../../aspose.words/textcolumncollection/spacing/) { get; set; } | Когда столбцы расположены равномерно, получает или задает расстояние между каждым столбцом в пунктах. |
| [Width](../../aspose.words/textcolumncollection/width/) { get; } | Когда столбцы расположены равномерно, получает ширину столбцов. |

## Методы

| Имя | Описание |
| --- | --- |
| [SetCount](../../aspose.words/textcolumncollection/setcount/)(int) | Располагает текст в указанное количество текстовых столбцов. |

### Примечания

Использовать[`SetCount`](./setcount/) установить количество текстовых столбцов.

Чтобы все столбцы были одинаковой ширины и располагались равномерно, установите[`EvenlySpaced`](./evenlyspaced/) к **истинный** и укажите расстояние между столбцами в[`Spacing`](./spacing/). MS Word будет автоматически рассчитывать ширину столбцов.

Если у вас есть **Равномерное расстояние** установлен в **ЛОЖЬ** вам необходимо указать ширину и интервал для каждого столбца отдельно. Используйте индексатор для доступа к отдельным[`TextColumn`](../textcolumn/) объекты.

При использовании пользовательской ширины столбцов убедитесь, что сумма ширины всех столбцов и интервалов между ними равна ширине страницы за вычетом левого и правого полей страницы.

### Примеры

Показывает, как создать несколько равномерно расположенных столбцов в разделе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


