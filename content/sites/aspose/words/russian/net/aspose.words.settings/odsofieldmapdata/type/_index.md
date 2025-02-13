---
title: OdsoFieldMapData.Type
second_title: Справочник по API Aspose.Words для .NET
description: OdsoFieldMapData свойство. Указывает сопоставлено ли данное поле слияния со столбцом в данном внешнем источнике данных или нет. Значение по умолчаниюDefault .
type: docs
weight: 50
url: /ru/net/aspose.words.settings/odsofieldmapdata/type/
---
## OdsoFieldMapData.Type property

Указывает, сопоставлено ли данное поле слияния со столбцом в данном внешнем источнике данных или нет. Значение по умолчанию:Default .

```csharp
public OdsoFieldMappingType Type { get; set; }
```

### Примеры

Показывает, как получить доступ к коллекции данных, которая сопоставляет столбцы источника данных с полями слияния.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// Эта коллекция определяет, как слияние почты будет отображать столбцы из источника данных
// в предопределенные поля MERGEFIELD, ADDRESSBLOCK и GREETINGLINE.
OdsoFieldMapDataCollection dataCollection = doc.MailMergeSettings.Odso.FieldMapDatas;
Assert.AreEqual(30, dataCollection.Count);

using (IEnumerator<OdsoFieldMapData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Field map data index {index++}, type \"{enumerator.Current.Type}\":");

        Console.WriteLine(
            enumerator.Current.Type != OdsoFieldMappingType.Null
                ? $"\tColumn \"{enumerator.Current.Name}\", number {enumerator.Current.Column} mapped to merge field \"{enumerator.Current.MappedName}\"."
                : "\tNo valid column to field mapping data present.");
    }
}

// Клонируем элементы этой коллекции.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Использовать элементы метода "RemoveAt" по отдельности по индексу.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// Используйте метод «Очистить», чтобы сразу очистить всю коллекцию.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Смотрите также

* enum [OdsoFieldMappingType](../../odsofieldmappingtype/)
* class [OdsoFieldMapData](../)
* пространство имен [Aspose.Words.Settings](../../odsofieldmapdata/)
* сборка [Aspose.Words](../../../)


