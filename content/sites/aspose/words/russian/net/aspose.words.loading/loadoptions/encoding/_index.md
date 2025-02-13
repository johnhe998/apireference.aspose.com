---
title: LoadOptions.Encoding
second_title: Справочник по API Aspose.Words для .NET
description: LoadOptions свойство. Получает или задает кодировку которая будет использоваться для загрузки документа HTML TXT или CHM если кодировка не указана внутри документа. Может быть нулевым. Значение по умолчанию  null.
type: docs
weight: 50
url: /ru/net/aspose.words.loading/loadoptions/encoding/
---
## LoadOptions.Encoding property

Получает или задает кодировку, которая будет использоваться для загрузки документа HTML, TXT или CHM, если кодировка не указана внутри документа. Может быть нулевым. Значение по умолчанию — null.

```csharp
public Encoding Encoding { get; set; }
```

### Примечания

Это свойство используется только при загрузке документов HTML, TXT или CHM.

Если внутри документа не указана кодировка и это свойство`нулевой`, то система попытается автоматически определить кодировку.

### Примеры

Показывает, как установить кодировку для открытия документа.

```csharp
// Объект FileFormatInfo обнаружит, что этот файл закодирован не в UTF-7.
FileFormatInfo fileFormatInfo = FileFormatUtil.DetectFileFormat(MyDir + "Encoded in UTF-7.txt");

Assert.AreNotEqual(Encoding.UTF7, fileFormatInfo.Encoding);

// Если мы загрузим документ без конфигураций загрузки, Aspose.Words обнаружит его кодировку как UTF-8.
Document doc = new Document(MyDir + "Encoded in UTF-7.txt");

// Содержимое, проанализированное в UTF-8, создает действительную строку.
// Однако, зная, что файл в кодировке UTF-7, мы видим, что результат неверный.
Assert.AreEqual("Hello world+ACE-", doc.ToString(SaveFormat.Text).Trim());

// В случаях неоднозначной кодировки, такой как эта, мы можем установить конкретный вариант кодировки
// для анализа файла в объекте LoadOptions.
LoadOptions loadOptions = new LoadOptions
{
    Encoding = Encoding.UTF7
};

// Загружаем документ при передаче объекта LoadOptions, затем проверяем содержимое документа.
doc = new Document(MyDir + "Encoded in UTF-7.txt", loadOptions);

Assert.AreEqual("Hello world!", doc.ToString(SaveFormat.Text).Trim());
```

### Смотрите также

* class [LoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../loadoptions/)
* сборка [Aspose.Words](../../../)


