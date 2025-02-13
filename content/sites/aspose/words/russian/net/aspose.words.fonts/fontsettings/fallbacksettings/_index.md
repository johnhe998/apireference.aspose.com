---
title: FontSettings.FallbackSettings
second_title: Справочник по API Aspose.Words для .NET
description: FontSettings свойство. Настройки связанные с резервным механизмом шрифта.
type: docs
weight: 30
url: /ru/net/aspose.words.fonts/fontsettings/fallbacksettings/
---
## FontSettings.FallbackSettings property

Настройки, связанные с резервным механизмом шрифта.

```csharp
public FontFallbackSettings FallbackSettings { get; }
```

### Примеры

Показывает, как распределять резервные шрифты по диапазонам кодов символов Unicode.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Настройте наши параметры шрифта так, чтобы исходные шрифты были только из папки «MyFonts».
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// Вызов метода "BuildAutomatic" сгенерирует резервную схему, которая
// распределяет доступные шрифты по как можно большему количеству кодов символов Unicode.
// В нашем случае он имеет доступ только к нескольким шрифтам в папке «MyFonts».
fontFallbackSettings.BuildAutomatic();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.BuildAutomatic.xml");

// Мы также можем загрузить пользовательскую схему подстановки из файла, подобного этому.
// Эта схема применяет шрифт «AllegroOpen» к блокам Unicode «0000-00ff», шрифт «AllegroOpen» к блокам «0100-024f»,
// и шрифт "M+ 2m" во всех других диапазонах, которые другие шрифты в схеме не охватывают.
fontFallbackSettings.Load(MyDir + "Custom font fallback settings.xml");

// Создайте конструктор документов и установите для него шрифт, которого нет ни в одном из наших источников.
// Наши настройки шрифта вызовут резервную схему для символов, которые мы набираем, используя недоступный шрифт.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Missing Font";

// Используйте построитель для печати каждого символа Unicode от 0x0021 до 0x052F,
// с описательными строками, разделяющими блоки Unicode, которые мы определили в нашей собственной схеме отката шрифта.
for (int i = 0x0021; i < 0x0530; i++)
{
    switch (i)
    {
        case 0x0021:
            builder.Writeln(
                "\n\n0x0021 - 0x00FF: \nBasic Latin/Latin-1 Supplement Unicode blocks in \"AllegroOpen\" font:");
            break;
        case 0x0100:
            builder.Writeln(
                "\n\n0x0100 - 0x024F: \nLatin Extended A/B blocks, mostly in \"AllegroOpen\" font:");
            break;
        case 0x0250:
            builder.Writeln("\n\n0x0250 - 0x052F: \nIPA/Greek/Cyrillic blocks in \"M+ 2m\" font:");
            break;
    }

    builder.Write($"{Convert.ToChar(i)}");
}

doc.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.pdf");
```

### Смотрите также

* class [FontFallbackSettings](../../fontfallbacksettings/)
* class [FontSettings](../)
* пространство имен [Aspose.Words.Fonts](../../fontsettings/)
* сборка [Aspose.Words](../../../)


