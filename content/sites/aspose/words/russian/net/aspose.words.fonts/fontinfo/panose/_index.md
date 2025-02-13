---
title: FontInfo.Panose
second_title: Справочник по API Aspose.Words для .NET
description: FontInfo свойство. Получает или задает классификационный номер гарнитуры шрифта PANOSE.
type: docs
weight: 60
url: /ru/net/aspose.words.fonts/fontinfo/panose/
---
## FontInfo.Panose property

Получает или задает классификационный номер гарнитуры шрифта PANOSE.

```csharp
public byte[] Panose { get; set; }
```

### Примечания

PANOSE — это компактное 10-байтовое описание важнейших визуальных характеристик шрифта, , таких как контрастность, насыщенность и стиль с засечками. Цифры обозначают вид семейства, стиль засечек, толщину , пропорцию, контрастность, вариацию штриха, стиль руки, форму буквы, среднюю линию и высоту по оси X.

Может быть`нулевой`.

### Примеры

Показывает, как получить доступ и распечатать сведения о каждом шрифте в документе.

```csharp
Document doc = new Document(MyDir + "Document.docx");

IEnumerator<FontInfo> fontCollectionEnumerator = doc.FontInfos.GetEnumerator();
while (fontCollectionEnumerator.MoveNext())
{
    FontInfo fontInfo = fontCollectionEnumerator.Current;
    if (fontInfo != null)
    {
        Console.WriteLine("Font name: " + fontInfo.Name);

        // Альтернативные имена обычно пусты.
        Console.WriteLine("Alt name: " + fontInfo.AltName);
        Console.WriteLine("\t- Family: " + fontInfo.Family);
        Console.WriteLine("\t- " + (fontInfo.IsTrueType ? "Is TrueType" : "Is not TrueType"));
        Console.WriteLine("\t- Pitch: " + fontInfo.Pitch);
        Console.WriteLine("\t- Charset: " + fontInfo.Charset);
        Console.WriteLine("\t- Panose:");
        Console.WriteLine("\t\tFamily Kind: " + fontInfo.Panose[0]);
        Console.WriteLine("\t\tSerif Style: " + fontInfo.Panose[1]);
        Console.WriteLine("\t\tWeight: " + fontInfo.Panose[2]);
        Console.WriteLine("\t\tProportion: " + fontInfo.Panose[3]);
        Console.WriteLine("\t\tContrast: " + fontInfo.Panose[4]);
        Console.WriteLine("\t\tStroke Variation: " + fontInfo.Panose[5]);
        Console.WriteLine("\t\tArm Style: " + fontInfo.Panose[6]);
        Console.WriteLine("\t\tLetterform: " + fontInfo.Panose[7]);
        Console.WriteLine("\t\tMidline: " + fontInfo.Panose[8]);
        Console.WriteLine("\t\tX-Height: " + fontInfo.Panose[9]);
    }
}
```

### Смотрите также

* class [FontInfo](../)
* пространство имен [Aspose.Words.Fonts](../../fontinfo/)
* сборка [Aspose.Words](../../../)


