---
title: Class CsvDataSource
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Reporting.CsvDataSource classe. Fornisce laccesso ai dati di un file CSV o di un flusso da utilizzare allinterno di un report.
type: docs
weight: 4410
url: /it/net/aspose.words.reporting/csvdatasource/
---
## CsvDataSource class

Fornisce l'accesso ai dati di un file CSV o di un flusso da utilizzare all'interno di un report.

```csharp
public class CsvDataSource
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [CsvDataSource](csvdatasource/#constructor)(Stream) | Crea una nuova origine dati con i dati di un flusso CSV utilizzando le opzioni predefinite per l'analisi dei dati CSV. |
| [CsvDataSource](csvdatasource/#constructor_2)(string) | Crea una nuova origine dati con i dati di un file CSV utilizzando le opzioni predefinite per l'analisi dei dati CSV. |
| [CsvDataSource](csvdatasource/#constructor_1)(Stream, CsvDataLoadOptions) | Crea una nuova origine dati con i dati di un flusso CSV utilizzando le opzioni specificate per l'analisi dei dati CSV. |
| [CsvDataSource](csvdatasource/#constructor_3)(string, CsvDataLoadOptions) | Crea una nuova origine dati con i dati di un file CSV utilizzando le opzioni specificate per l'analisi dei dati CSV. |

### Osservazioni

Per accedere ai dati del file o del flusso corrispondente durante la generazione di un report, passare un'istanza di questa classe come un'origine dati a uno dei[`ReportingEngine`](../reportingengine/) .BuildReport sovraccarichi.

Nei documenti modello, a`CsvDataSource` l'istanza dovrebbe essere trattata come se fosse aDataTable istanza. Per ulteriori informazioni, vedere riferimento alla sintassi del modello (https://docs.aspose.com/display/wordsnet/Template+Syntax).

I tipi di dati dei valori separati da virgole vengono determinati automaticamente in base alle loro rappresentazioni di stringa. Quindi, nei documenti template , puoi lavorare con valori digitati anziché solo stringhe. Il motore è in grado di riconoscere automaticamente i valori dei seguenti tipi:

* Nullable
* Nullable
* Nullable
* Nullable
* String

Si noti che affinché il riconoscimento automatico dei tipi di dati funzioni, le rappresentazioni di stringa di valori separati da virgole devono essere formate utilizzando impostazioni cultura invarianti.

Per ignorare il comportamento predefinito del caricamento dei dati CSV, inizializzare e passare a[`CsvDataLoadOptions`](../csvdataloadoptions/)instance a un costruttore di questa classe.

### Guarda anche

* spazio dei nomi [Aspose.Words.Reporting](../../aspose.words.reporting/)
* assemblea [Aspose.Words](../../)


