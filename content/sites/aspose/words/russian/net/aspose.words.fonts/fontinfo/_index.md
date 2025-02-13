---
title: Class FontInfo
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fonts.FontInfo сорт. Указывает информацию о шрифте используемом в документе.
type: docs
weight: 2740
url: /ru/net/aspose.words.fonts/fontinfo/
---
## FontInfo class

Указывает информацию о шрифте, используемом в документе.

```csharp
public class FontInfo
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [AltName](../../aspose.words.fonts/fontinfo/altname/) { get; set; } | Получает или задает альтернативное имя шрифта. |
| [Charset](../../aspose.words.fonts/fontinfo/charset/) { get; set; } | Получает или задает набор символов для шрифта. |
| [Family](../../aspose.words.fonts/fontinfo/family/) { get; set; } | Получает или задает семейство шрифтов, к которому принадлежит этот шрифт. |
| [IsTrueType](../../aspose.words.fonts/fontinfo/istruetype/) { get; set; } | Указывает, что данный шрифт является шрифтом TrueType или OpenType, а не растровым или векторным шрифтом. Значение по умолчанию — true. |
| [Name](../../aspose.words.fonts/fontinfo/name/) { get; } | Получает имя шрифта. |
| [Panose](../../aspose.words.fonts/fontinfo/panose/) { get; set; } | Получает или задает классификационный номер гарнитуры шрифта PANOSE. |
| [Pitch](../../aspose.words.fonts/fontinfo/pitch/) { get; set; } | Шаг указывает, является ли шрифт фиксированным шагом, пропорциональным интервалом или зависит от настройки по умолчанию. |

## Методы

| Имя | Описание |
| --- | --- |
| [GetEmbeddedFont](../../aspose.words.fonts/fontinfo/getembeddedfont/)(EmbeddedFontFormat, EmbeddedFontStyle) | Получает определенный встроенный файл шрифта. |
| [GetEmbeddedFontAsOpenType](../../aspose.words.fonts/fontinfo/getembeddedfontasopentype/)(EmbeddedFontStyle) | Получает встроенный файл шрифта в формате OpenType. Шрифты в формате Embedded OpenType конвертируются в OpenType. |

### Примечания

Вы не создаете экземпляры этого класса напрямую. Используйте[`FontInfos`](../../aspose.words/documentbase/fontinfos/) для доступа к коллекции шрифтов , определенных в документе.

### Примеры

Показывает, как напечатать сведения о том, какие шрифты присутствуют в документе.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Печатаем все используемые и неиспользуемые шрифты в документе.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

### Смотрите также

* пространство имен [Aspose.Words.Fonts](../../aspose.words.fonts/)
* сборка [Aspose.Words](../../)


