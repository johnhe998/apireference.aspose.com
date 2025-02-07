---
title: FontInfo.Name
second_title: Справочник по API Aspose.Words для .NET
description: FontInfo свойство. Получает имя шрифта.
type: docs
weight: 50
url: /ru/net/aspose.words.fonts/fontinfo/name/
---
## FontInfo.Name property

Получает имя шрифта.

```csharp
public string Name { get; }
```

### Примечания

Не может быть`нулевой`. Может быть пустой строкой.

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

* class [FontInfo](../)
* пространство имен [Aspose.Words.Fonts](../../fontinfo/)
* сборка [Aspose.Words](../../../)


