---
title: PdfSaveOptions.UseCoreFonts
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Получает или задает значение определяющее следует ли заменять шрифты TrueType Arial Times New Roman Courier New и Symbol базовыми шрифтами PDF Type 1.
type: docs
weight: 280
url: /ru/net/aspose.words.saving/pdfsaveoptions/usecorefonts/
---
## PdfSaveOptions.UseCoreFonts property

Получает или задает значение, определяющее, следует ли заменять шрифты TrueType Arial, Times New Roman, Courier New и Symbol базовыми шрифтами PDF Type 1.

```csharp
public bool UseCoreFonts { get; set; }
```

### Примечания

Значение по умолчанию`ЛОЖЬ` . Когда это значение установлено на`истинный` Шрифты Arial, Times New Roman, Courier New и Symbol заменяются в документе PDF соответствующим базовым шрифтом Type 1.

Основные шрифты PDF или их метрики шрифтов и подходящие замещающие шрифты должны быть доступны для любого приложения для просмотра PDF.

Этот параметр работает только для текста в кодировке ANSI (Windows-1252). Текст, отличный от ANSI, будет написан встроенным шрифтом TrueType независимо от этого параметра.

Соответствие форматам PDF/A и PDF/UA требует внедрения всех шрифтов.`ЛОЖЬ` значение будет использоваться автоматически при сохранении в PDF/A и PDF/UA.

Основные шрифты не поддерживаются при сохранении в формате PDF 2.0.`ЛОЖЬ`значение будет использоваться автоматически при сохранении в PDF 2.0.

Эта опция имеет более высокий приоритет, чем[`FontEmbeddingMode`](../fontembeddingmode/) вариант.

### Примеры

Показывает, как включить/выключить замену шрифта PDF Type 1.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Установите для свойства "UseCoreFonts" значение "true", чтобы заменить некоторые шрифты,
// включение двух шрифтов в наш документ с их эквивалентами PDF Type 1.
// Установите для свойства «UseCoreFonts» значение «false», чтобы не применять шрифты PDF Type 1.
options.UseCoreFonts = useCoreFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf", options);

if (useCoreFonts)
    Assert.That(3000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
else
    Assert.That(30000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
```

### Смотрите также

* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


