---
title: IWarningCallback.Warning
second_title: Справочник по API Aspose.Words для .NET
description: IWarningCallback метод. Aspose.Words вызывает этот метод когда во время загрузки документа или сохранения возникает проблема которая может привести к потере форматирования или точности данных.
type: docs
weight: 10
url: /ru/net/aspose.words/iwarningcallback/warning/
---
## IWarningCallback.Warning method

Aspose.Words вызывает этот метод, когда во время загрузки документа или сохранения возникает проблема, которая может привести к потере форматирования или точности данных.

```csharp
public void Warning(WarningInfo info)
```

### Примеры

Показывает, как задать свойство для поиска ближайшего соответствия отсутствующему шрифту из доступных источников шрифтов.

```csharp
[Test]
public void EnableFontSubstitution()
{
    // Откройте документ, содержащий текст, отформатированный шрифтом, которого нет ни в одном из наших источников шрифтов.
    Document doc = new Document(MyDir + "Missing font.docx");

    // Назначаем обратный вызов для обработки предупреждений о замене шрифта.
    HandleDocumentSubstitutionWarnings substitutionWarningHandler = new HandleDocumentSubstitutionWarnings();
    doc.WarningCallback = substitutionWarningHandler;

    // Установите имя шрифта по умолчанию и включите замену шрифта.
    FontSettings fontSettings = new FontSettings();
    fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
    ;
    fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;

    // Мы получим предупреждение о замене шрифта, если сохраним документ с отсутствующим шрифтом.
    doc.FontSettings = fontSettings;
    doc.Save(ArtifactsDir + "FontSettings.EnableFontSubstitution.pdf");

    using (IEnumerator<WarningInfo> warnings = substitutionWarningHandler.FontWarnings.GetEnumerator())
        while (warnings.MoveNext())
            Console.WriteLine(warnings.Current.Description);

    // Мы также можем проверять предупреждения в коллекции и очищать их.
    Assert.AreEqual(WarningSource.Layout, substitutionWarningHandler.FontWarnings[0].Source);
    Assert.AreEqual(
        "Font '28 Days Later' has not been found. Using 'Calibri' font instead. Reason: alternative name from document.",
        substitutionWarningHandler.FontWarnings[0].Description);

    substitutionWarningHandler.FontWarnings.Clear();

    Assert.That(substitutionWarningHandler.FontWarnings, Is.Empty);
}

public class HandleDocumentSubstitutionWarnings : IWarningCallback
{
    /// <summary>
    /// Вызывается каждый раз, когда возникает предупреждение во время загрузки/сохранения.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

### Смотрите также

* class [WarningInfo](../../warninginfo/)
* interface [IWarningCallback](../)
* пространство имен [Aspose.Words](../../iwarningcallback/)
* сборка [Aspose.Words](../../../)


