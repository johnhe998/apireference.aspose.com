---
title: Enum PdfTextCompression
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.PdfTextCompression перечисление. Определяет тип сжатия применяемый ко всему содержимому файла PDF кроме изображений.
type: docs
weight: 5250
url: /ru/net/aspose.words.saving/pdftextcompression/
---
## PdfTextCompression enumeration

Определяет тип сжатия, применяемый ко всему содержимому файла PDF, кроме изображений.

```csharp
public enum PdfTextCompression
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Без сжатия. |
| Flate | `1` | Flate (ZIP) сжатие. |

### Примеры

Показывает, как применять сжатие текста при сохранении документа в формате PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

for (int i = 0; i < 100; i++)
    builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                    "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Установите для свойства "TextCompression" значение "PdfTextCompression.None", чтобы не применять
// сжатие в текст при сохранении документа в PDF.
// Установите для свойства "TextCompression" значение "PdfTextCompression.Flate", чтобы применить сжатие ZIP
// в текст, когда мы сохраняем документ в формате PDF. Чем больше документ, тем большее влияние он окажет.
options.TextCompression = pdfTextCompression;

doc.Save(ArtifactsDir + "PdfSaveOptions.TextCompression.pdf", options);
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


