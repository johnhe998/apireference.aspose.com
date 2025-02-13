---
title: FontFallbackSettings.BuildAutomatic
second_title: Справочник по API Aspose.Words для .NET
description: FontFallbackSettings метод. Автоматически создает резервные настройки путем сканирования доступных шрифтов.
type: docs
weight: 10
url: /ru/net/aspose.words.fonts/fontfallbacksettings/buildautomatic/
---
## FontFallbackSettings.BuildAutomatic method

Автоматически создает резервные настройки путем сканирования доступных шрифтов.

```csharp
public void BuildAutomatic()
```

### Примечания

Этот метод может привести к неоптимальным резервным настройкам. Шрифты проверяются[ Диапазон символов Юникода](https://docs.microsoft.com/en-us/typography/opentype/spec/os2#ur) полей, а не по фактическому наличию глифов. Также диапазоны Unicode проверяются индивидуально , и несколько диапазонов, относящихся к одному языку/сценарию, могут использовать разные резервные шрифты.

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

* class [FontFallbackSettings](../)
* пространство имен [Aspose.Words.Fonts](../../fontfallbacksettings/)
* сборка [Aspose.Words](../../../)


