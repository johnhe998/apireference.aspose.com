---
title: Style.IsHeading
second_title: Справочник по API Aspose.Words для .NET
description: Style свойство. Истинно если стиль является одним из встроенных стилей заголовков.
type: docs
weight: 60
url: /ru/net/aspose.words/style/isheading/
---
## Style.IsHeading property

Истинно, если стиль является одним из встроенных стилей заголовков.

```csharp
public bool IsHeading { get; }
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

* class [Style](../)
* пространство имен [Aspose.Words](../../style/)
* сборка [Aspose.Words](../../../)


