---
title: Class StreamFontSource
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fonts.StreamFontSource сорт. Базовый класс для определяемого пользователем источника потокового шрифта.
type: docs
weight: 2860
url: /ru/net/aspose.words.fonts/streamfontsource/
---
## StreamFontSource class

Базовый класс для определяемого пользователем источника потокового шрифта.

```csharp
public abstract class StreamFontSource : FontSourceBase
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/streamfontsource/cachekey/) { get; } | Ключ этого источника в кеше. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Возвращает приоритет источника шрифта. |
| [Type](../../aspose.words.fonts/streamfontsource/type/) { get; } | Возвращает тип источника шрифта. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Вызывается во время обработки источника шрифта при обнаружении проблемы, которая может привести к потере точности форматирования. |

## Методы

| Имя | Описание |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Возвращает список шрифтов, доступных через этот источник. |
| abstract [OpenFontDataStream](../../aspose.words.fonts/streamfontsource/openfontdatastream/)() | Этот метод должен открывать поток с данными шрифта по запросу. |

### Примечания

Чтобы использовать источник шрифта потока, вы должны создать производный класс от`StreamFontSource` и обеспечить реализацию[`OpenFontDataStream`](./openfontdatastream/) метод.

[`OpenFontDataStream`](./openfontdatastream/)метод может вызываться несколько раз. Впервые он будет называться , когда Aspose.Words просканирует предоставленные источники шрифтов, чтобы получить список доступных шрифтов. Позже он может быть вызван, если шрифт используется в документе для анализа данных шрифта и внедрения данных шрифта в некоторые форматы вывода.

`StreamFontSource` может быть полезным, поскольку позволяет загружать данные шрифта только тогда, когда это требуется , а не хранить их в памяти для[`FontSettings`](../fontsettings/) продолжительность жизни.

### Примеры

Показывает, как загружать шрифты из потока.

```csharp
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.SetFontsSources(new FontSourceBase[] {new StreamFontSourceFile()});

    DocumentBuilder builder = new DocumentBuilder();
    builder.Document.FontSettings = fontSettings;
    builder.Font.Name = "Kreon-Regular";
    builder.Writeln("Test aspose text when saving to PDF.");

    builder.Document.Save(ArtifactsDir + "FontSettings.StreamFontSourceFileRendering.pdf");
}

/// <summary>
/// Загружаем данные шрифта только при необходимости, а не сохраняем их в памяти
/// на все время жизни объекта FontSettings.
/// </summary>
private class StreamFontSourceFile : StreamFontSource
{
    public override Stream OpenFontDataStream()
    {
        return File.OpenRead(FontsDir + "Kreon-Regular.ttf");
    }
}
```

### Смотрите также

* class [FontSourceBase](../fontsourcebase/)
* пространство имен [Aspose.Words.Fonts](../../aspose.words.fonts/)
* сборка [Aspose.Words](../../)


