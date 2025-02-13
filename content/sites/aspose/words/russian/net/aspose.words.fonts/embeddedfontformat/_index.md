---
title: Enum EmbeddedFontFormat
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fonts.EmbeddedFontFormat перечисление. Определяет формат конкретного встроенного шрифта внутриFontInfo объект.
type: docs
weight: 2670
url: /ru/net/aspose.words.fonts/embeddedfontformat/
---
## EmbeddedFontFormat enumeration

Определяет формат конкретного встроенного шрифта внутри[`FontInfo`](../fontinfo/) объект.

При сохранении документа в файл записываются только встроенные шрифты соответствующего формата.

```csharp
public enum EmbeddedFontFormat
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| EmbeddedOpenType | `0` | Указывает встроенный формат файла OpenType (EOT). |
| OpenType | `1` | Определяет шрифт, встроенный как обычная копия файла шрифта OpenType (TrueType). |

### Примеры

Показывает, как извлечь встроенный шрифт из документа и сохранить его в локальной файловой системе.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfo embeddedFont = doc.FontInfos["Alte DIN 1451 Mittelschrift"];
byte[] embeddedFontBytes = embeddedFont.GetEmbeddedFont(EmbeddedFontFormat.OpenType, EmbeddedFontStyle.Regular);
File.WriteAllBytes(ArtifactsDir + "Alte DIN 1451 Mittelschrift.ttf", embeddedFontBytes);

// Форматы встроенных шрифтов могут отличаться в других форматах, таких как .doc.
// Нам нужно знать правильный формат, прежде чем мы сможем извлечь шрифт.
doc = new Document(MyDir + "Embedded font.doc");

Assert.IsNull(doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFont(EmbeddedFontFormat.OpenType, EmbeddedFontStyle.Regular));
Assert.IsNotNull(doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFont(EmbeddedFontFormat.EmbeddedOpenType, EmbeddedFontStyle.Regular));

// Кроме того, мы можем преобразовать встроенный формат OpenType, полученный из документов .doc, в OpenType.
embeddedFontBytes = doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFontAsOpenType(EmbeddedFontStyle.Regular);

File.WriteAllBytes(ArtifactsDir + "Alte DIN 1451 Mittelschrift.otf", embeddedFontBytes);
```

### Смотрите также

* пространство имен [Aspose.Words.Fonts](../../aspose.words.fonts/)
* сборка [Aspose.Words](../../)


