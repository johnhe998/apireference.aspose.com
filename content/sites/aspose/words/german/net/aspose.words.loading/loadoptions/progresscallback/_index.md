---
title: LoadOptions.ProgressCallback
second_title: Aspose.Words für .NET-API-Referenz
description: LoadOptions eigendom. Wird beim Laden eines Dokuments aufgerufen und nimmt Daten zum Ladefortschritt entgegen.
type: docs
weight: 130
url: /de/net/aspose.words.loading/loadoptions/progresscallback/
---
## LoadOptions.ProgressCallback property

Wird beim Laden eines Dokuments aufgerufen und nimmt Daten zum Ladefortschritt entgegen.

```csharp
public IDocumentLoadingCallback ProgressCallback { get; set; }
```

### Bemerkungen

Docx ,FlatOpc ,Docm ,Dotm ,Dotx ,Markdown ,Rtf ,WordML ,Doc ,Dot ,Odt ,Ott Formate unterstützt.

### Beispiele

Zeigt, wie der Benutzer benachrichtigt wird, wenn das Laden des Dokuments die erwartete Ladezeit überschreitet.

```csharp
[Test]
public void ProgressCallback()
{
    LoadingProgressCallback progressCallback = new LoadingProgressCallback();

    LoadOptions loadOptions = new LoadOptions { ProgressCallback = progressCallback };

    try
    {
        Document doc = new Document(MyDir + "Big document.docx", loadOptions);
    }
    catch (OperationCanceledException exception)
    {
        Console.WriteLine(exception.Message);

        // Problem mit der Ladedauer behandeln.
    }
}

/// <summary>
/// Brechen Sie das Laden eines Dokuments nach "MaxDuration" Sekunden ab.
/// </summary>
public class LoadingProgressCallback : IDocumentLoadingCallback
{
    /// <summary>
    /// Ctr.
    /// </summary>
    public LoadingProgressCallback()
    {
        mLoadingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// Callback-Methode, die beim Laden des Dokuments aufgerufen wurde.
    /// </summary>
    /// <param name="args">Lade Argumente.</param>
    public void Notify(DocumentLoadingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mLoadingStartedAt).TotalSeconds;

        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// Datum und Uhrzeit, wann das Laden des Dokuments gestartet wird.
    /// </summary>
    private readonly DateTime mLoadingStartedAt;

    /// <summary>
    /// Maximal erlaubte Dauer in Sek.
    /// </summary>
    private const double MaxDuration = 0.5;
}
```

### Siehe auch

* interface [IDocumentLoadingCallback](../../idocumentloadingcallback/)
* class [LoadOptions](../)
* namensraum [Aspose.Words.Loading](../../loadoptions/)
* Montage [Aspose.Words](../../../)


