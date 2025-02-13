---
title: BuiltInDocumentProperties.HeadingPairs
second_title: Справочник по API Aspose.Words для .NET
description: BuiltInDocumentProperties свойство. Определяет заголовки документов и их имена.
type: docs
weight: 110
url: /ru/net/aspose.words.properties/builtindocumentproperties/headingpairs/
---
## BuiltInDocumentProperties.HeadingPairs property

Определяет заголовки документов и их имена.

```csharp
public object[] HeadingPairs { get; set; }
```

### Примечания

Каждая пара заголовков занимает два элемента в этом массиве.

Первым элементом пары являетсяString и указывает название заголовка. Второй элемент пары — этоInt32 и указывает количество частей document для этого заголовка в[`TitlesOfParts`](../titlesofparts/) имущество.

Общая сумма счетчиков для всех пар заголовков в этом ресурсе должна быть равна числу элементов в[`TitlesOfParts`](../titlesofparts/) имущество.

Aspose.Words не обновляет это свойство.

### Примеры

Показывает взаимосвязь между свойствами "HeadingPairs" и "TitlesOfParts".

```csharp
Document doc = new Document(MyDir + "Heading pairs and titles of parts.docx");

// Мы можем найти объединенные значения этих коллекций через
// "Файл" -> "Свойства" -> "Дополнительные свойства" -> Вкладка «Содержание».
// Свойство HeadingPairs представляет собой набор <string, int> пары, которые
// определяет, сколько частей документа охватывает заголовок.
object[] headingPairs = doc.BuiltInDocumentProperties.HeadingPairs;

// Свойство TitlesOfParts содержит имена частей, принадлежащих вышеуказанным заголовкам.
string[] titlesOfParts = doc.BuiltInDocumentProperties.TitlesOfParts;

int headingPairsIndex = 0;
int titlesOfPartsIndex = 0;
while (headingPairsIndex < headingPairs.Length)
{
    Console.WriteLine($"Parts for {headingPairs[headingPairsIndex++]}:");
    int partsCount = Convert.ToInt32(headingPairs[headingPairsIndex++]);

    for (int i = 0; i < partsCount; i++)
        Console.WriteLine($"\t\"{titlesOfParts[titlesOfPartsIndex++]}\"");
}
```

### Смотрите также

* class [BuiltInDocumentProperties](../)
* пространство имен [Aspose.Words.Properties](../../builtindocumentproperties/)
* сборка [Aspose.Words](../../../)


