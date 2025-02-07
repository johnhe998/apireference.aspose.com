---
title: Class FontSubstitutionSettings
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fonts.FontSubstitutionSettings сорт. Задает настройки механизма подстановки шрифтов.
type: docs
weight: 2830
url: /ru/net/aspose.words.fonts/fontsubstitutionsettings/
---
## FontSubstitutionSettings class

Задает настройки механизма подстановки шрифтов.

```csharp
public class FontSubstitutionSettings
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [DefaultFontSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/defaultfontsubstitution/) { get; } | Настройки, связанные с правилом замены шрифта по умолчанию. |
| [FontConfigSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontconfigsubstitution/) { get; } | Настройки, связанные с правилом подстановки конфигурации шрифта. |
| [FontInfoSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontinfosubstitution/) { get; } | Настройки, связанные с правилом подстановки информации о шрифте. |
| [FontNameSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontnamesubstitution/) { get; } | Настройки, связанные с правилом подстановки имени шрифта. |
| [TableSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/tablesubstitution/) { get; } | Настройки, связанные с правилом подстановки таблиц. |

### Примечания

Процесс замены шрифта состоит из нескольких правил, которые проверяются одно за другим в определенном порядке. Если первое правило не может разрешить шрифт, то проверяется второе правило и так далее.

Порядок правил следующий: 1. Правило подстановки имени шрифта (по умолчанию включено) 2. Правило подстановки конфигурации шрифта (по умолчанию отключено) 3. Правило подстановки таблицы (по умолчанию включено) 4. Правило подстановки информации о шрифте (включено по умолчанию) 5. Правило шрифта по умолчанию (включено по умолчанию)

Обратите внимание, что правило подстановки информации о шрифте всегда разрешает шрифт, если[`FontInfo`](../fontinfo/) доступен и переопределит правило шрифта по умолчанию. Если вы хотите использовать правило шрифта по умолчанию, вам следует отключить правило подстановки информации о шрифте .

Обратите внимание, что правило подстановки конфигурации шрифта разрешает шрифт в большинстве случаев и, таким образом, переопределяет все другие правила.

### Примеры

Показывает, как получить доступ к источнику системного шрифта документа и установить заменители шрифта.

```csharp
Document doc = new Document();
doc.FontSettings = new FontSettings();

// По умолчанию пустой документ всегда содержит системный источник шрифта.
Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);

SystemFontSource systemFontSource = (SystemFontSource) doc.FontSettings.GetFontsSources()[0];
Assert.AreEqual(FontSourceType.SystemFonts, systemFontSource.Type);
Assert.AreEqual(0, systemFontSource.Priority);

PlatformID pid = Environment.OSVersion.Platform;
bool isWindows = (pid == PlatformID.Win32NT) || (pid == PlatformID.Win32S) ||
                 (pid == PlatformID.Win32Windows) || (pid == PlatformID.WinCE);
if (isWindows)
{
    const string fontsPath = @"C:\WINDOWS\Fonts";
    Assert.AreEqual(fontsPath.ToLower(),
        SystemFontSource.GetSystemFontFolders().FirstOrDefault()?.ToLower());
}

foreach (string systemFontFolder in SystemFontSource.GetSystemFontFolders())
{
    Console.WriteLine(systemFontFolder);
}

// Установите шрифт, существующий в каталоге шрифтов Windows, в качестве замены несуществующего.
doc.FontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;
doc.FontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Kreon-Regular", new[] {"Calibri"});

Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
Assert.Contains("Calibri",
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").ToArray());

// В качестве альтернативы мы могли бы добавить папку источника шрифта, в которой соответствующая папка содержит шрифт.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
doc.FontSettings.SetFontsSources(new FontSourceBase[] {systemFontSource, folderFontSource});
Assert.AreEqual(2, doc.FontSettings.GetFontsSources().Length);

// Сброс источников шрифта по-прежнему оставляет нам источник системного шрифта, а также наши заменители.
doc.FontSettings.ResetFontSources();

Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);
Assert.AreEqual(FontSourceType.SystemFonts, doc.FontSettings.GetFontsSources()[0].Type);
Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
```

### Смотрите также

* пространство имен [Aspose.Words.Fonts](../../aspose.words.fonts/)
* сборка [Aspose.Words](../../)


