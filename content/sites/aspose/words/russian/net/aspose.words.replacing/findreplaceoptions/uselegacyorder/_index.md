---
title: FindReplaceOptions.UseLegacyOrder
second_title: Справочник по API Aspose.Words для .NET
description: FindReplaceOptions свойство. True указывает что текстовый поиск выполняется последовательно сверху вниз с учетом текстовых полей. Значение по умолчанию  false.
type: docs
weight: 150
url: /ru/net/aspose.words.replacing/findreplaceoptions/uselegacyorder/
---
## FindReplaceOptions.UseLegacyOrder property

True указывает, что текстовый поиск выполняется последовательно сверху вниз с учетом текстовых полей. Значение по умолчанию — false.

```csharp
public bool UseLegacyOrder { get; set; }
```

### Примеры

Показывает, как изменить порядок поиска узлов при выполнении операции поиска и замены текста.

```csharp
[TestCase(true)] // ExSkip
[TestCase(false)] // ExSkip
public void UseLegacyOrder(bool useLegacyOrder)
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Вставляем три прогона, которые мы можем найти, используя шаблон регулярного выражения.
    // Поместите один из этих запусков в текстовое поле.
    builder.Writeln("[tag 1]");
    Shape textBox = builder.InsertShape(ShapeType.TextBox, 100, 50);
    builder.Writeln("[tag 2]");
    builder.MoveTo(textBox.FirstParagraph);
    builder.Write("[tag 3]");

    // Мы можем использовать объект «FindReplaceOptions», чтобы изменить процесс поиска и замены.
    FindReplaceOptions options = new FindReplaceOptions();

    // Назначаем пользовательский обратный вызов свойству «ReplacingCallback».
    TextReplacementTracker callback = new TextReplacementTracker();
    options.ReplacingCallback = callback;

    // Если мы установим для свойства "UseLegacyOrder" значение "true",
    // операция поиска и замены будет проходить через все прогоны за пределами текстового поля
    // прежде чем переходить к тем, которые находятся внутри текстового поля.
    // Если мы установим для свойства "UseLegacyOrder" значение "false",
    // операция поиска и замены будет проходить по всем запускам в диапазоне в последовательном порядке.
    options.UseLegacyOrder = useLegacyOrder;

    doc.Range.Replace(new Regex(@"\[tag \d*\]"), "", options);

    Assert.AreEqual(useLegacyOrder ?
        new List<string> { "[tag 1]", "[tag 3]", "[tag 2]" } :
        new List<string> { "[tag 1]", "[tag 2]", "[tag 3]" }, callback.Matches);
}

/// <summary>
/// Записывает порядок всех совпадений, возникающих во время операции поиска и замены.
/// </summary>
private class TextReplacementTracker : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs e)
    {
        Matches.Add(e.Match.Value);
        return ReplaceAction.Replace;
    }

    public List<string> Matches { get; } = new List<string>();
}
```

### Смотрите также

* class [FindReplaceOptions](../)
* пространство имен [Aspose.Words.Replacing](../../findreplaceoptions/)
* сборка [Aspose.Words](../../../)


