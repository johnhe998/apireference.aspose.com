---
title: ChartCategory
second_title: Справочник по API Aspose.Slides для .NET
description: Представляет категории диаграмм.
type: docs
weight: 1130
url: /ru/net/aspose.slides.charts/chartcategory/
---
## ChartCategory class

Представляет категории диаграмм.

```csharp
public class ChartCategory : IChartCategory
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [AsCell](../../aspose.slides.charts/chartcategory/ascell) { get; set; } | Возвращает или задает объект IChartDataCell. Если категория многоуровневая, то используется объект IChartDataCell для уровня "0". Чтение/запись[`IChartDataCell`](../ichartdatacell). |
| [AsLiteral](../../aspose.slides.charts/chartcategory/asliteral) { get; set; } | Возвращает или устанавливает объект AsLiteral. Чтение/записьObject. |
| [GroupingLevels](../../aspose.slides.charts/chartcategory/groupinglevels) { get; } | Управляемый контейнер значений уровней группировки категорий диаграммы. Многоуровневая категория содержит более одного уровня группировки. Индексация уровней группировки начинается с нуля. Только для чтения[`IChartCategoryLevelsManager`](../ichartcategorylevelsmanager). |
| [UseCell](../../aspose.slides.charts/chartcategory/usecell) { get; } | Если true, то свойство AsCell актуально. Другими словами, рабочий лист используется для хранения категории (в этом случае поддерживается многоуровневая категория). Если false, то актуально свойство AsLiteral. Другими словами, рабочий лист НЕ используется для хранения категории (и этот случай не поддерживает многоуровневые категории). Только чтениеBoolean. |
| [Value](../../aspose.slides.charts/chartcategory/value) { get; set; } | Если UseCell равно true, то это свойство представляет свойство AsCell.Value. Если UseCell имеет значение false, то это свойство представляет свойство AsLiteral. Чтение/записьObject. |

## Методы

| Имя | Описание |
| --- | --- |
| [Remove](../../aspose.slides.charts/chartcategory/remove)() | Удаляет категорию из диаграммы. |

### Смотрите также

* interface [IChartCategory](../ichartcategory)
* пространство имен [Aspose.Slides.Charts](../../aspose.slides.charts)
* сборка [Aspose.Slides](../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
