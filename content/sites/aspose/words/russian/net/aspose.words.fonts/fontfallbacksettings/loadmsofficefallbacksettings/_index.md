---
title: FontFallbackSettings.LoadMsOfficeFallbackSettings
second_title: Справочник по API Aspose.Words для .NET
description: FontFallbackSettings метод. Загружает предопределенные резервные настройки имитирующие резервный вариант Microsoft Word и использующие офисные шрифты Microsoft.
type: docs
weight: 30
url: /ru/net/aspose.words.fonts/fontfallbacksettings/loadmsofficefallbacksettings/
---
## FontFallbackSettings.LoadMsOfficeFallbackSettings method

Загружает предопределенные резервные настройки, имитирующие резервный вариант Microsoft Word и использующие офисные шрифты Microsoft.

```csharp
public void LoadMsOfficeFallbackSettings()
```

### Примеры

Показывает, как загрузить предварительно определенные настройки резервного шрифта.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Сохраняем резервную схему шрифта по умолчанию в XML-документ.
// Например, один из элементов имеет значение «0C00-0C7F» для Range и соответствующее значение «Vani» для FallbackFonts.
// Это означает, что если шрифт, который используется в каком-то тексте, не имеет символов для блока 0x0C00-0x0C7F Unicode,
// резервная схема будет использовать символы из заменителя шрифта "Vani".
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.Default.xml");

// Ниже приведены две предопределенные схемы отката шрифтов, которые мы можем выбрать.
// 1 — использовать схему Microsoft Office по умолчанию, которая совпадает со стандартной:
fontFallbackSettings.LoadMsOfficeFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadMsOfficeFallbackSettings.xml");

// 2 - Используйте схему, построенную из шрифтов Google Noto:
fontFallbackSettings.LoadNotoFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadNotoFallbackSettings.xml");
```

### Смотрите также

* class [FontFallbackSettings](../)
* пространство имен [Aspose.Words.Fonts](../../fontfallbacksettings/)
* сборка [Aspose.Words](../../../)


