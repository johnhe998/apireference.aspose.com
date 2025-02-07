---
title: Class FontInfoCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fonts.FontInfoCollection сорт. Представляет набор шрифтов используемых в документе.
type: docs
weight: 2750
url: /ru/net/aspose.words.fonts/fontinfocollection/
---
## FontInfoCollection class

Представляет набор шрифтов, используемых в документе.

```csharp
public class FontInfoCollection : IEnumerable<FontInfo>
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words.fonts/fontinfocollection/count/) { get; } | Получает количество элементов, содержащихся в коллекции. |
| [EmbedSystemFonts](../../aspose.words.fonts/fontinfocollection/embedsystemfonts/) { get; set; } | Указывает, следует ли встраивать системные шрифты в документ. Значение по умолчанию для этого свойства: **ЛОЖЬ**. |
| [EmbedTrueTypeFonts](../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) { get; set; } | Указывает, следует ли встраивать шрифты TrueType в документ при его сохранении. Значение по умолчанию для этого свойства: **ЛОЖЬ** . |
| [Item](../../aspose.words.fonts/fontinfocollection/item/) { get; } | Получает шрифт с указанным именем. (2 indexers) |
| [SaveSubsetFonts](../../aspose.words.fonts/fontinfocollection/savesubsetfonts/) { get; set; } | Указывает, следует ли сохранять вместе с документом подмножество встроенных шрифтов TrueType. Значение по умолчанию для этого свойства: **ЛОЖЬ**. |

## Методы

| Имя | Описание |
| --- | --- |
| [Contains](../../aspose.words.fonts/fontinfocollection/contains/)(string) | Определяет, содержит ли коллекция шрифт с заданным именем. |
| [GetEnumerator](../../aspose.words.fonts/fontinfocollection/getenumerator/)() | Возвращает объект перечислителя, который можно использовать для перебора всех элементов в коллекции. |

### Примечания

Предметы[`FontInfo`](../fontinfo/) объекты.

Вы не создаете экземпляры этого класса напрямую. Используйте[`FontInfos`](../../aspose.words/documentbase/fontinfos/) для доступа к коллекции шрифтов , определенной в документе.

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

Показывает, как сохранить документ со встроенными шрифтами TrueType.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Смотрите также

* class [FontInfo](../fontinfo/)
* пространство имен [Aspose.Words.Fonts](../../aspose.words.fonts/)
* сборка [Aspose.Words](../../)


