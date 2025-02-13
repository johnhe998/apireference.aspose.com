---
title: Class AsposeWordsPrintDocument
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Rendering.AsposeWordsPrintDocument сорт. Обеспечивает реализацию по умолчанию для печатиDocument в среде печати .NET.
type: docs
weight: 4280
url: /ru/net/aspose.words.rendering/asposewordsprintdocument/
---
## AsposeWordsPrintDocument class

Обеспечивает реализацию по умолчанию для печати[`Document`](../../aspose.words/document/) в среде печати .NET.

```csharp
public class AsposeWordsPrintDocument : PrintDocument
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [AsposeWordsPrintDocument](asposewordsprintdocument/)(Document) | Инициализирует новый экземпляр этого класса. |

## Методы

| Имя | Описание |
| --- | --- |
| [CachePrinterSettings](../../aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/)() | Читает и кэширует некоторые поляPrinterSettings для сокращения времени печати. |

### Примечания

`AsposeWordsPrintDocument` отменяетPrintEventArgs) для печати диапазона страниц, указанного вPrinterSettings.

Один документ Word может состоять из нескольких разделов, в которых указаны страницы разных размеров, ориентации и лотков для бумаги.`AsposeWordsPrintDocument` переопределяет QueryPageSettingsEventArgs) чтобы правильно выбрать размер бумаги, ориентацию и источник бумаги при печати документа Word.

Microsoft Word хранит значения лотков для бумаги, специфичные для принтера, в документе Word, и поэтому только для печати на той же модели принтера, которая была выбрана, когда пользователь указал лотки для бумаги , что приведет к печати из правильных лотков. Если вы печатаете документ на другом принтере, то скорее всего будет использоваться лоток для бумаги по умолчанию, а не лотки, указанные в документе.

### Смотрите также

* пространство имен [Aspose.Words.Rendering](../../aspose.words.rendering/)
* сборка [Aspose.Words](../../)


