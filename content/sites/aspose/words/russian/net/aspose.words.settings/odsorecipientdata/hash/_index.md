---
title: OdsoRecipientData.Hash
second_title: Справочник по API Aspose.Words для .NET
description: OdsoRecipientData свойство. Представляет хэшкод для этой записи. Иногда Microsoft Word используетHash целой записи вместоUniqueTag value. Значение по умолчанию 0.
type: docs
weight: 40
url: /ru/net/aspose.words.settings/odsorecipientdata/hash/
---
## OdsoRecipientData.Hash property

Представляет хэш-код для этой записи. Иногда Microsoft Word использует`Hash` целой записи вместо[`UniqueTag`](../uniquetag/) value. Значение по умолчанию: 0.

```csharp
public int Hash { get; set; }
```

### Примеры

Показывает, как получить доступ к набору данных, который указывает, какие записи источника данных слияния будут исключены при слиянии.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

OdsoRecipientDataCollection dataCollection = doc.MailMergeSettings.Odso.RecipientDatas;

Assert.AreEqual(70, dataCollection.Count);

using (IEnumerator<OdsoRecipientData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine(
            $"Odso recipient data index {index++} will {(enumerator.Current.Active ? "" : "not ")}be imported upon mail merge.");
        Console.WriteLine($"\tColumn #{enumerator.Current.Column}");
        Console.WriteLine($"\tHash code: {enumerator.Current.Hash}");
        Console.WriteLine($"\tContents array length: {enumerator.Current.UniqueTag.Length}");
    }
}

// Мы можем клонировать элементы этой коллекции.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Мы также можем удалить элементы по отдельности или очистить всю коллекцию сразу.
dataCollection.RemoveAt(0);

Assert.AreEqual(69, dataCollection.Count);

dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Смотрите также

* class [OdsoRecipientData](../)
* пространство имен [Aspose.Words.Settings](../../odsorecipientdata/)
* сборка [Aspose.Words](../../../)


