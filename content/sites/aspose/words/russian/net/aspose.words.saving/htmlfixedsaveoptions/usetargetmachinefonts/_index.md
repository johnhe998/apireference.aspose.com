---
title: HtmlFixedSaveOptions.UseTargetMachineFonts
second_title: Справочник по API Aspose.Words для .NET
description: HtmlFixedSaveOptions свойство. Флаг указывает должны ли шрифты с целевой машины использоваться для отображения документа. Если для этого флага установлено значение trueFontFormat а такжеExportEmbeddedFontsсвойства не действуют такжеResourceSavingCallback не срабатывает для шрифтов. Значение по умолчанию  false.
type: docs
weight: 190
url: /ru/net/aspose.words.saving/htmlfixedsaveoptions/usetargetmachinefonts/
---
## HtmlFixedSaveOptions.UseTargetMachineFonts property

Флаг указывает, должны ли шрифты с целевой машины использоваться для отображения документа. Если для этого флага установлено значение true,[`FontFormat`](../fontformat/) а также[`ExportEmbeddedFonts`](../exportembeddedfonts/)свойства не действуют, также[`ResourceSavingCallback`](../resourcesavingcallback/) не срабатывает для шрифтов. Значение по умолчанию — false.

```csharp
public bool UseTargetMachineFonts { get; set; }
```

### Примеры

Показывает, как использовать шрифты только с целевого компьютера при сохранении документа в формате HTML.

```csharp
Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedCss = true,
    UseTargetMachineFonts = useTargetMachineFonts,
    FontFormat = ExportFontFormat.Ttf,
    ExportEmbeddedFonts = false,
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html");

if (useTargetMachineFonts)
    Assert.False(Regex.Match(outDocContents, "@font-face").Success);
else
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], " +
        "url[(]'HtmlFixedSaveOptions.UsingMachineFonts/font001.ttf'[)] format[(]'truetype'[)]; }").Success);
```

### Смотрите также

* class [HtmlFixedSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* сборка [Aspose.Words](../../../)


