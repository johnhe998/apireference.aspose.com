---
title: LoadOptions.WarningCallback
second_title: Aspose.Words per .NET API Reference
description: LoadOptions proprietà. Chiamato durante unoperazione di caricamento quando viene rilevato un problema che potrebbe comportare una perdita di fedeltà dei dati o della formattazione.
type: docs
weight: 170
url: /it/net/aspose.words.loading/loadoptions/warningcallback/
---
## LoadOptions.WarningCallback property

Chiamato durante un'operazione di caricamento, quando viene rilevato un problema che potrebbe comportare una perdita di fedeltà dei dati o della formattazione.

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### Esempi

Mostra come stampare e memorizzare gli avvisi che si verificano durante il caricamento del documento.

```csharp
{
    // Crea un nuovo oggetto LoadOptions e imposta il suo attributo WarningCallback
    // come istanza della nostra implementazione IWarningCallback.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.WarningCallback = new DocumentLoadingWarningCallback();

    // La nostra richiamata stamperà tutti gli avvisi che vengono visualizzati durante l'operazione di caricamento.
    Document doc = new Document(MyDir + "Document.docx", loadOptions);

    List<WarningInfo> warnings = ((DocumentLoadingWarningCallback)loadOptions.WarningCallback).GetWarnings();
    Assert.AreEqual(3, warnings.Count);

/// <summary>
/// IWarningCallback che stampa gli avvisi e i relativi dettagli man mano che si verificano durante il caricamento del documento.
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

### Guarda anche

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [LoadOptions](../)
* spazio dei nomi [Aspose.Words.Loading](../../loadoptions/)
* assemblea [Aspose.Words](../../../)


