---
title: LoadOptions.WarningCallback
second_title: Справочник по API Aspose.Words для .NET
description: LoadOptions свойство. Вызывается во время операции загрузки при обнаружении проблемы которая может привести к потере точности данных или форматирования.
type: docs
weight: 170
url: /ru/net/aspose.words.loading/loadoptions/warningcallback/
---
## LoadOptions.WarningCallback property

Вызывается во время операции загрузки при обнаружении проблемы, которая может привести к потере точности данных или форматирования.

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### Примеры

Показывает, как распечатать и сохранить предупреждения, возникающие при загрузке документа.

```csharp
{
    // Создаем новый объект LoadOptions и устанавливаем его атрибут WarningCallback
    // как экземпляр нашей реализации IWarningCallback.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.WarningCallback = new DocumentLoadingWarningCallback();

    // Наш обратный вызов напечатает все предупреждения, которые появляются во время операции загрузки.
    Document doc = new Document(MyDir + "Document.docx", loadOptions);

    List<WarningInfo> warnings = ((DocumentLoadingWarningCallback)loadOptions.WarningCallback).GetWarnings();
    Assert.AreEqual(3, warnings.Count);

/// <summary>
/// IWarningCallback, который выводит предупреждения и их детали по мере их возникновения во время загрузки документа.
/// </summary>
private class DocumentLoadingWarningCallback : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        Console.WriteLine($"Warning: {info.WarningType}");
        Console.WriteLine($"\tSource: {info.Source}");
        Console.WriteLine($"\tDescription: {info.Description}");
        mWarnings.Add(info);
    }

    public List<WarningInfo> GetWarnings()
    {
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### Смотрите также

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [LoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../loadoptions/)
* сборка [Aspose.Words](../../../)


