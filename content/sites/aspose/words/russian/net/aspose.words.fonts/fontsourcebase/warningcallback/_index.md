---
title: FontSourceBase.WarningCallback
second_title: Справочник по API Aspose.Words для .NET
description: FontSourceBase свойство. Вызывается во время обработки источника шрифта при обнаружении проблемы которая может привести к потере точности форматирования.
type: docs
weight: 30
url: /ru/net/aspose.words.fonts/fontsourcebase/warningcallback/
---
## FontSourceBase.WarningCallback property

Вызывается во время обработки источника шрифта при обнаружении проблемы, которая может привести к потере точности форматирования.

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### Примеры

Показывает, как вызвать обратный вызов предупреждения при работе с источниками шрифта.

```csharp
[Test]
public void FontSourceWarning()
{
    FontSettings settings = new FontSettings();
    settings.SetFontsFolder("bad folder?", false);

    FontSourceBase source = settings.GetFontsSources()[0];
    FontSourceWarningCollector callback = new FontSourceWarningCollector();
    source.WarningCallback = callback;

    // Получить список шрифтов для вызова предупреждающего обратного вызова.
    IList<PhysicalFontInfo> fontInfos = source.GetAvailableFonts();

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Contains("Error loading font from the folder \"bad folder?\""));
}

private class FontSourceWarningCollector : IWarningCallback
{
    /// <summary>
    /// Вызывается каждый раз, когда возникает предупреждение при обработке источника шрифта.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        FontSubstitutionWarnings.Warning(info);
    }

    public readonly WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

### Смотрите также

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [FontSourceBase](../)
* пространство имен [Aspose.Words.Fonts](../../fontsourcebase/)
* сборка [Aspose.Words](../../../)


