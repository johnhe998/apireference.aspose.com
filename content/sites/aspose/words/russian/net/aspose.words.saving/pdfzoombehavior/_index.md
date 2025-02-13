---
title: Enum PdfZoomBehavior
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.PdfZoomBehavior перечисление. Определяет тип масштабирования применяемый к PDFдокументу при его открытии в программе просмотра PDF.
type: docs
weight: 5260
url: /ru/net/aspose.words.saving/pdfzoombehavior/
---
## PdfZoomBehavior enumeration

Определяет тип масштабирования, применяемый к PDF-документу при его открытии в программе просмотра PDF.

```csharp
public enum PdfZoomBehavior
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Способ отображения документа остается за программой просмотра PDF. Обычно средство просмотра отображает документ по ширине страницы. |
| ZoomFactor | `1` | Отображает страницу с указанным коэффициентом масштабирования. |
| FitPage | `2` | Отображает страницу так, чтобы она была видна полностью. |
| FitWidth | `3` | По ширине страницы. |
| FitHeight | `4` | Соответствует высоте страницы. |
| FitBox | `5` | Соответствует ограничивающей рамке (прямоугольнику, содержащему все видимые элементы на странице). |

### Примеры

Показывает, как установить масштабирование по умолчанию, применяемое программой чтения при открытии обработанного PDF-документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
// Установите свойство "ZoomBehavior" в "PdfZoomBehavior.ZoomFactor", чтобы программа для чтения PDF
// применяем коэффициент масштабирования в процентах, когда мы открываем документ с его помощью.
// Установите для свойства "ZoomFactor" значение "25", чтобы присвоить коэффициенту масштабирования значение 25%.
PdfSaveOptions options = new PdfSaveOptions
{
    ZoomBehavior = PdfZoomBehavior.ZoomFactor,
    ZoomFactor = 25
};

// Когда мы откроем этот документ с помощью программы для чтения, такой как Adobe Acrobat, мы увидим, что документ масштабируется до 1/4 его фактического размера.
doc.Save(ArtifactsDir + "PdfSaveOptions.ZoomBehaviour.pdf", options);
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


