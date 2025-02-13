---
title: DropDownItemCollection.Item
second_title: Справочник по API Aspose.Words для .NET
description: DropDownItemCollection свойство. Получает или задает элемент по указанному индексу.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/dropdownitemcollection/item/
---
## DropDownItemCollection indexer

Получает или задает элемент по указанному индексу.

```csharp
public string this[int index] { get; set; }
```

### Примеры

Показывает, как вставить поле со списком и изменить элементы в его коллекции элементов.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте поле со списком, а затем проверьте его набор раскрывающихся элементов.
// В Microsoft Word пользователь щелкнет поле со списком,
// а затем выберите один из элементов текста в коллекции для отображения.
string[] items = { "One", "Two", "Three" };
FormField comboBoxField = builder.InsertComboBox("DropDown", items, 0);
DropDownItemCollection dropDownItems = comboBoxField.DropDownItems;

Assert.AreEqual(3, dropDownItems.Count);
Assert.AreEqual("One", dropDownItems[0]);
Assert.AreEqual(1, dropDownItems.IndexOf("Two"));
Assert.IsTrue(dropDownItems.Contains("Three"));

// Есть два способа добавления нового элемента в существующую коллекцию элементов раскрывающегося списка.
// 1 - Добавить элемент в конец коллекции:
dropDownItems.Add("Four");

// 2 - Вставить элемент перед другим элементом по указанному индексу:
dropDownItems.Insert(3, "Three and a half");

Assert.AreEqual(5, dropDownItems.Count);

// Перебираем коллекцию и печатаем каждый элемент.
using (IEnumerator<string> dropDownCollectionEnumerator = dropDownItems.GetEnumerator())
    while (dropDownCollectionEnumerator.MoveNext())
        Console.WriteLine(dropDownCollectionEnumerator.Current);

// Существует два способа удаления элементов из набора раскрывающихся элементов.
// 1 - Удалить элемент с содержимым, равным переданной строке:
dropDownItems.Remove("Four");

// 2 - Удалить элемент по индексу:
dropDownItems.RemoveAt(3);

Assert.AreEqual(3, dropDownItems.Count);
Assert.IsFalse(dropDownItems.Contains("Three and a half"));
Assert.IsFalse(dropDownItems.Contains("Four"));

doc.Save(ArtifactsDir + "FormFields.DropDownItemCollection.html");

// Очистить всю коллекцию раскрывающихся элементов.
dropDownItems.Clear();
```

### Смотрите также

* class [DropDownItemCollection](../)
* пространство имен [Aspose.Words.Fields](../../dropdownitemcollection/)
* сборка [Aspose.Words](../../../)


