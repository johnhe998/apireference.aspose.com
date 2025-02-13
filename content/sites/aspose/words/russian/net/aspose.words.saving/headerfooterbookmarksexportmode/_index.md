---
title: Enum HeaderFooterBookmarksExportMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.HeaderFooterBookmarksExportMode перечисление. Указывает как экспортируются закладки в верхних/нижних колонтитулах.
type: docs
weight: 4790
url: /ru/net/aspose.words.saving/headerfooterbookmarksexportmode/
---
## HeaderFooterBookmarksExportMode enumeration

Указывает, как экспортируются закладки в верхних/нижних колонтитулах.

```csharp
public enum HeaderFooterBookmarksExportMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Закладки в верхних/нижних колонтитулах не экспортируются. |
| First | `1` | Экспортируется только закладка в первом верхнем/нижнем колонтитуле раздела. |
| All | `2` | Экспортируются закладки во всех верхних/нижних колонтитулах. |

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


