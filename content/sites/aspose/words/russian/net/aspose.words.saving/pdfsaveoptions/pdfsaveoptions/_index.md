---
title: PdfSaveOptions.PdfSaveOptions
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions строитель. Инициализирует новый экземпляр этого класса который можно использовать для сохранения документа в папке .Pdf формат.
type: docs
weight: 10
url: /ru/net/aspose.words.saving/pdfsaveoptions/pdfsaveoptions/
---
## PdfSaveOptions constructor

Инициализирует новый экземпляр этого класса, который можно использовать для сохранения документа в папке .Pdf формат.

```csharp
public PdfSaveOptions()
```

### Примеры

Показывает, как включить или отключить подмножество при встраивании шрифтов во время рендеринга документа в PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Arvo";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Настройте наши источники шрифтов, чтобы убедиться, что у нас есть доступ к обоим шрифтам в этом документе.
FontSourceBase[] originalFontsSources = FontSettings.DefaultInstance.GetFontsSources();
Aspose.Words.Fonts.FolderFontSource folderFontSource = new Aspose.Words.Fonts.FolderFontSource(FontsDir, true);
FontSettings.DefaultInstance.SetFontsSources(new[] { originalFontsSources[0], folderFontSource });

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(fontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Поскольку наш документ содержит пользовательский шрифт, может потребоваться его встраивание в выходной документ.
// Установите для свойства "EmbedFullFonts" значение "true", чтобы встроить каждый глиф каждого встроенного шрифта в выходной PDF-файл.
// Размер документа может стать очень большим, но мы сможем полностью использовать все шрифты, если редактируем PDF.
// Установите для свойства "EmbedFullFonts" значение "false", чтобы применить подмножество к шрифтам, сохраняя только глифы
// который использует документ. Файл будет значительно меньше,
// но нам может понадобиться доступ к любым пользовательским шрифтам, если мы редактируем документ.
options.EmbedFullFonts = embedFullFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf", options);

if (embedFullFonts)
    Assert.That(500000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));
else
    Assert.That(25000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));

// Восстановить исходные источники шрифтов.
FontSettings.DefaultInstance.SetFontsSources(originalFontsSources);
```

### Смотрите также

* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


