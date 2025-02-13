---
title: Class OdsoFieldMapData
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Settings.OdsoFieldMapData сорт. Указывает как столбец во внешнем источнике данных должен быть сопоставлен с предопределенными полями слияния в документе.
type: docs
weight: 5600
url: /ru/net/aspose.words.settings/odsofieldmapdata/
---
## OdsoFieldMapData class

Указывает, как столбец во внешнем источнике данных должен быть сопоставлен с предопределенными полями слияния в документе.

```csharp
public class OdsoFieldMapData
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [OdsoFieldMapData](odsofieldmapdata/)() | Конструктор по умолчанию. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [Column](../../aspose.words.settings/odsofieldmapdata/column/) { get; set; } | Указывает отсчитываемый от нуля индекс столбца во внешнем источнике данных, который должен быть сопоставлен с локальным именем определенного поля MERGEFIELD. Значение по умолчанию: 0. |
| [MappedName](../../aspose.words.settings/odsofieldmapdata/mappedname/) { get; set; } | Указывает предопределенное имя поля слияния, которое должно быть сопоставлено с номером столбца , указанным[`Column`](./column/) свойство в этом сопоставлении полей. Значение по умолчанию — пустая строка. |
| [Name](../../aspose.words.settings/odsofieldmapdata/name/) { get; set; } | Указывает имя столбца во внешнем источнике данных для столбца, индекс которого указан параметром[`Column`](./column/) property. Значение по умолчанию — пустая строка. |
| [Type](../../aspose.words.settings/odsofieldmapdata/type/) { get; set; } | Указывает, сопоставлено ли данное поле слияния со столбцом в данном внешнем источнике данных или нет. Значение по умолчанию:Default . |

## Методы

| Имя | Описание |
| --- | --- |
| [Clone](../../aspose.words.settings/odsofieldmapdata/clone/)() | Возвращает глубокий клон этого объекта. |

### Примечания

Microsoft Word предоставляет некоторые предопределенные имена полей слияния, которые он позволяет вставлять в документ как MERGEFIELD или использовать в полях ADDRESSBLOCK или GREETINGLINE. Информация, указанная в`OdsoFieldMapData` позволяет сопоставить один столбец внешнего источника данных с одним предопределенным полем слияния.

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

* пространство имен [Aspose.Words.Settings](../../aspose.words.settings/)
* сборка [Aspose.Words](../../)


