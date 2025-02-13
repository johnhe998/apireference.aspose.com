---
title: Class OutlineOptions
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.OutlineOptions сорт. Позволяет указать параметры контура.
type: docs
weight: 5080
url: /ru/net/aspose.words.saving/outlineoptions/
---
## OutlineOptions class

Позволяет указать параметры контура.

```csharp
public class OutlineOptions
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [OutlineOptions](outlineoptions/)() | Конструктор по умолчанию. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [BookmarksOutlineLevels](../../aspose.words.saving/outlineoptions/bookmarksoutlinelevels/) { get; } | Позволяет указать уровень структуры отдельных закладок. |
| [CreateMissingOutlineLevels](../../aspose.words.saving/outlineoptions/createmissingoutlinelevels/) { get; set; } | Получает или задает значение, определяющее, создавать ли отсутствующие уровни структуры при экспорте документа . |
| [CreateOutlinesForHeadingsInTables](../../aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/) { get; set; } | Указывает, создавать ли контуры для заголовков (абзацев, отформатированных с помощью стилей заголовков) внутри таблиц. |
| [DefaultBookmarksOutlineLevel](../../aspose.words.saving/outlineoptions/defaultbookmarksoutlinelevel/) { get; set; } | Указывает уровень по умолчанию в структуре документа, на котором должны отображаться закладки Word. |
| [ExpandedOutlineLevels](../../aspose.words.saving/outlineoptions/expandedoutlinelevels/) { get; set; } | Указывает, сколько уровней в структуре документа должно отображаться в расширенном виде при просмотре файла. |
| [HeadingsOutlineLevels](../../aspose.words.saving/outlineoptions/headingsoutlinelevels/) { get; set; } | Указывает, сколько уровней заголовков (абзацев, отформатированных с помощью стилей заголовков) включить в структуру документа . |

### Примеры

Показывает, как обрабатывать закладки в верхних/нижних колонтитулах в документе, который мы преобразуем в PDF.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Установите для свойства "PageMode" значение "PdfPageMode.UseOutlines", чтобы отобразить панель навигации схемы в выходном PDF-файле.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// Установите для свойства "DefaultBookmarksOutlineLevel" значение "1", чтобы отобразить все
// закладки на первом уровне схемы в выходном PDF.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// Установите для свойства "HeaderFooterBookmarksExportMode" значение "HeaderFooterBookmarksExportMode.None", чтобы
// не экспортировать закладки внутри верхних/нижних колонтитулов.
// Установите для свойства "HeaderFooterBookmarksExportMode" значение "HeaderFooterBookmarksExportMode.First", чтобы
// экспортировать закладки только в верхний/нижний колонтитулы первого раздела.
// Установите для свойства "HeaderFooterBookmarksExportMode" значение "HeaderFooterBookmarksExportMode.All", чтобы
// экспортировать закладки, которые есть во всех верхних/нижних колонтитулах.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


