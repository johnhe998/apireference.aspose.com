---
title: Style.Styles
second_title: Справочник по API Aspose.Words для .NET
description: Style свойство. Получает коллекцию стилей к которым принадлежит этот стиль.
type: docs
weight: 150
url: /ru/net/aspose.words/style/styles/
---
## Style.Styles property

Получает коллекцию стилей, к которым принадлежит этот стиль.

```csharp
public StyleCollection Styles { get; }
```

### Примеры

Показывает, как получить доступ к коллекции стилей документа.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// Перечислить и перечислить все стили, которые документ, созданный с помощью Aspose.Words, содержит по умолчанию.
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
```

### Смотрите также

* class [StyleCollection](../../stylecollection/)
* class [Style](../)
* пространство имен [Aspose.Words](../../style/)
* сборка [Aspose.Words](../../../)


