---
title: NodeList.ToArray
second_title: Справочник по API Aspose.Words для .NET
description: NodeList метод. Копирует все узлы из коллекции в новый массив узлов.
type: docs
weight: 40
url: /ru/net/aspose.words/nodelist/toarray/
---
## NodeList.ToArray method

Копирует все узлы из коллекции в новый массив узлов.

```csharp
public Node[] ToArray()
```

### Возвращаемое значение

Массив узлов.

### Примечания

Вы не должны добавлять/удалять узлы при переборе коллекции узлов, потому что это делает итератор недействительным и требует обновления для живых коллекций.

Чтобы иметь возможность добавлять/удалять узлы во время итерации, используйте этот метод для копирования узлов в массив фиксированного размера, а затем выполните итерацию по массиву.

### Примеры

Показывает, как выбрать определенные узлы с помощью выражения XPath.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Это выражение извлечет все узлы абзаца,
// которые являются потомками любого узла таблицы в документе.
NodeList nodeList = doc.SelectNodes("//Таблица//Абзац");

// Проходим по списку с помощью перечислителя и печатаем содержимое каждого абзаца в каждой ячейке таблицы.
int index = 0;

using (IEnumerator<Node> e = nodeList.GetEnumerator())
    while (e.MoveNext())
        Console.WriteLine($"Table paragraph index {index++}, contents: \"{e.Current.GetText().Trim()}\"");

// Это выражение выберет любые абзацы, которые являются прямыми дочерними элементами любого узла Body в документе.
nodeList = doc.SelectNodes("//Тело/Абзац");

// Мы можем рассматривать список как массив.
Assert.AreEqual(4, nodeList.ToArray().Length);

// Используйте SelectSingleNode, чтобы выбрать первый результат того же выражения, что и выше.
Node node = doc.SelectSingleNode("//Тело/Абзац");

Assert.AreEqual(typeof(Paragraph), node.GetType());
```

### Смотрите также

* class [Node](../../node/)
* class [NodeList](../)
* пространство имен [Aspose.Words](../../nodelist/)
* сборка [Aspose.Words](../../../)


