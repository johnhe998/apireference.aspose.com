---
title: SaveOptions.AllowEmbeddingPostScriptFonts
second_title: Справочник по API Aspose.Words для .NET
description: SaveOptions свойство. Возвращает или задает логическое значение указывающее разрешать ли встраивание шрифтов с помощью PostScript layouts при встраивании шрифтов TrueType в документ после его сохранения. Значение по умолчанию ЛОЖЬ .
type: docs
weight: 20
url: /ru/net/aspose.words.saving/saveoptions/allowembeddingpostscriptfonts/
---
## SaveOptions.AllowEmbeddingPostScriptFonts property

Возвращает или задает логическое значение, указывающее, разрешать ли встраивание шрифтов с помощью PostScript layouts при встраивании шрифтов TrueType в документ после его сохранения. Значение по умолчанию: **ЛОЖЬ** .

```csharp
public bool AllowEmbeddingPostScriptFonts { get; set; }
```

### Примечания

Обратите внимание: Word не встраивает шрифты PostScript, но может открывать документы со встроенными шрифтами этого типа.

Этот вариант работает только тогда, когда[`EmbedTrueTypeFonts`](../../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) из [`FontInfos`](../../../aspose.words/documentbase/fontinfos/) свойство установлено на`истинный`.

### Примеры

Показывает, как сохранить документ со шрифтом PostScript.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "PostScriptFont";
builder.Writeln("Some text with PostScript font.");

// Загрузите шрифт с PostScript для использования в документе.
MemoryFontSource otf = new MemoryFontSource(File.ReadAllBytes(FontsDir + "AllegroOpen.otf"));
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] { otf });

// Встроить шрифты TrueType.
doc.FontInfos.EmbedTrueTypeFonts = true;

// Разрешить встраивание шрифтов PostScript при встраивании шрифтов TrueType.
// Microsoft Word не встраивает шрифты PostScript, но может открывать документы со встроенными шрифтами этого типа.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Docx);
saveOptions.AllowEmbeddingPostScriptFonts = true;

doc.Save(ArtifactsDir + "Document.AllowEmbeddingPostScriptFonts.docx", saveOptions);
```

### Смотрите также

* class [SaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../saveoptions/)
* сборка [Aspose.Words](../../../)


