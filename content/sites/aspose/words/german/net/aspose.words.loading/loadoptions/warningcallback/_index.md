---
title: LoadOptions.WarningCallback
second_title: Aspose.Words für .NET-API-Referenz
description: LoadOptions eigendom. Wird während eines Ladevorgangs aufgerufen wenn ein Problem erkannt wird das zu einem Verlust der Daten oder der Formatierung führen kann.
type: docs
weight: 170
url: /de/net/aspose.words.loading/loadoptions/warningcallback/
---
## LoadOptions.WarningCallback property

Wird während eines Ladevorgangs aufgerufen, wenn ein Problem erkannt wird, das zu einem Verlust der Daten oder der Formatierung führen kann.

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### Beispiele

Zeigt, wie Warnungen gedruckt und gespeichert werden, die während des Einlegens von Dokumenten auftreten.

```csharp
{
    // Ein neues LoadOptions-Objekt erstellen und sein WarningCallback-Attribut setzen
    // als Instanz unserer IWarningCallback-Implementierung.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.WarningCallback = new DocumentLoadingWarningCallback();

    // Unser Callback gibt alle Warnungen aus, die während des Ladevorgangs auftreten.
    Document doc = new Document(MyDir + "Document.docx", loadOptions);

    List<WarningInfo> warnings = ((DocumentLoadingWarningCallback)loadOptions.WarningCallback).GetWarnings();
    Assert.AreEqual(3, warnings.Count);

/// <summary>
/// IWarningCallback, der Warnungen und deren Details ausgibt, wenn sie während des Ladens des Dokuments auftreten.
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

### Siehe auch

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [LoadOptions](../)
* namensraum [Aspose.Words.Loading](../../loadoptions/)
* Montage [Aspose.Words](../../../)


