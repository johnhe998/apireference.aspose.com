---
title: HtmlFixedSaveOptions.ExportEmbeddedFonts
second_title: Справочник по API Aspose.Words для .NET
description: HtmlFixedSaveOptions свойство. Указывает должны ли шрифты быть встроены в HTMLдокумент в формате Base64. Обратите внимание что установка этого флага может значительно увеличить размер выходного HTMLфайла.
type: docs
weight: 50
url: /ru/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedfonts/
---
## HtmlFixedSaveOptions.ExportEmbeddedFonts property

Указывает, должны ли шрифты быть встроены в HTML-документ в формате Base64. Обратите внимание, что установка этого флага может значительно увеличить размер выходного HTML-файла.

```csharp
public bool ExportEmbeddedFonts { get; set; }
```

### Примеры

Показывает, как определить, где хранить встроенные шрифты при экспорте документа в HTML.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

// Когда мы экспортируем документ со встроенными шрифтами в .html,
// Aspose.Words может размещать шрифты в двух возможных местах.
// Установка флага «ExportEmbeddedFonts» в значение «true» будет хранить необработанные данные для встроенных шрифтов в таблице стилей CSS,
// в свойстве "url" правила "@font-face". Это может создать огромный файл таблицы стилей CSS.
// и уменьшите количество внешних файлов, которые создаст это преобразование HTML.
// Установка этого флага в "false" создаст файл для каждого шрифта.
// Таблица стилей CSS будет ссылаться на каждый файл шрифта, используя свойство "url" правила "@font-face".
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedFonts = exportEmbeddedFonts
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts/styles.css");

if (exportEmbeddedFonts)
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(].+[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(0, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(]'font001[.]woff'[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(2, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
```

### Смотрите также

* class [HtmlFixedSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* сборка [Aspose.Words](../../../)


