---
title: Enum TxtExportHeadersFootersMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.TxtExportHeadersFootersMode перечисление. Определяет способ экспорта верхних и нижних колонтитулов в обычный текстовый формат.
type: docs
weight: 5360
url: /ru/net/aspose.words.saving/txtexportheadersfootersmode/
---
## TxtExportHeadersFootersMode enumeration

Определяет способ экспорта верхних и нижних колонтитулов в обычный текстовый формат.

```csharp
public enum TxtExportHeadersFootersMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Верхние и нижние колонтитулы не экспортируются. |
| PrimaryOnly | `1` | Экспортируются только основные верхние и нижние колонтитулы в начале и конце каждого раздела. |
| AllAtEnd | `2` | Все верхние и нижние колонтитулы размещаются после всех разделов в самом конце документа. |

### Примеры

Показывает, как указать, как экспортировать верхние и нижние колонтитулы в обычный текстовый формат.

```csharp
Document doc = new Document();

// Вставляем в документ четные и первичные верхние/нижние колонтитулы.
// Первичные верхние/нижние колонтитулы переопределяют четные верхние/нижние колонтитулы.
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderEven].AppendParagraph("Even header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterEven].AppendParagraph("Even footer");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].AppendParagraph("Primary header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].AppendParagraph("Primary footer");

// Вставьте страницы для отображения этих верхних и нижних колонтитулов.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2");
builder.InsertBreak(BreakType.PageBreak); 
builder.Write("Page 3");

// Создаем объект "TxtSaveOptions", который мы можем передать в метод "Сохранить" документа
// чтобы изменить способ сохранения документа в виде открытого текста.
TxtSaveOptions saveOptions = new TxtSaveOptions();

// Установите для свойства "ExportHeadersFootersMode" значение "TxtExportHeadersFootersMode.None"
// чтобы не экспортировать верхние/нижние колонтитулы.
// Установите для свойства "ExportHeadersFootersMode" значение "TxtExportHeadersFootersMode.PrimaryOnly"
// для экспорта только основных верхних/нижних колонтитулов.
// Установите для свойства "ExportHeadersFootersMode" значение "TxtExportHeadersFootersMode.AllAtEnd"
// чтобы разместить все верхние и нижние колонтитулы для всех тел разделов в конце документа.
saveOptions.ExportHeadersFootersMode = txtExportHeadersFootersMode;

doc.Save(ArtifactsDir + "TxtSaveOptions.ExportHeadersFooters.txt", saveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.ExportHeadersFooters.txt");

switch (txtExportHeadersFootersMode)
{
    case TxtExportHeadersFootersMode.AllAtEnd:
        Assert.AreEqual("Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n" +
                        "Even header\r\n\r\n" +
                        "Primary header\r\n\r\n" +
                        "Even footer\r\n\r\n" +
                        "Primary footer\r\n\r\n", docText);
        break;
    case TxtExportHeadersFootersMode.PrimaryOnly:
        Assert.AreEqual("Primary header\r\n" +
                        "Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n" +
                        "Primary footer\r\n", docText);
        break;
    case TxtExportHeadersFootersMode.None:
        Assert.AreEqual("Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n", docText);
        break;
}
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


