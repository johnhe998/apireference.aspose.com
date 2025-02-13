---
title: Class XmlDataSource
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Reporting.XmlDataSource classe. Fornisce laccesso ai dati di un file o flusso XML da utilizzare allinterno di un report.
type: docs
weight: 4490
url: /it/net/aspose.words.reporting/xmldatasource/
---
## XmlDataSource class

Fornisce l'accesso ai dati di un file o flusso XML da utilizzare all'interno di un report.

```csharp
public class XmlDataSource
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [XmlDataSource](xmldatasource/#constructor)(Stream) | Crea una nuova origine dati con i dati da un flusso XML utilizzando le opzioni predefinite per il caricamento dei dati XML. |
| [XmlDataSource](xmldatasource/#constructor_4)(string) | Crea una nuova origine dati con i dati di un file XML utilizzando le opzioni predefinite per il caricamento dei dati XML. |
| [XmlDataSource](xmldatasource/#constructor_2)(Stream, Stream) | Crea una nuova origine dati con i dati da un flusso XML utilizzando un flusso XML Schema Definition. Le opzioni predefinite vengono utilizzate per il caricamento dei dati XML. |
| [XmlDataSource](xmldatasource/#constructor_1)(Stream, XmlDataLoadOptions) | Crea una nuova origine dati con i dati da un flusso XML utilizzando le opzioni specificate per il caricamento dei dati XML. |
| [XmlDataSource](xmldatasource/#constructor_6)(string, string) | Crea una nuova origine dati con i dati di un file XML utilizzando un file XML Schema Definition. Le opzioni predefinite vengono utilizzate per il caricamento dei dati XML. |
| [XmlDataSource](xmldatasource/#constructor_5)(string, XmlDataLoadOptions) | Crea una nuova origine dati con i dati di un file XML utilizzando le opzioni specificate per il caricamento dei dati XML. |
| [XmlDataSource](xmldatasource/#constructor_3)(Stream, Stream, XmlDataLoadOptions) | Crea una nuova origine dati con i dati da un flusso XML utilizzando un flusso XML Schema Definition. Le opzioni specificate vengono utilizzate per il caricamento dei dati XML. |
| [XmlDataSource](xmldatasource/#constructor_7)(string, string, XmlDataLoadOptions) | Crea una nuova origine dati con i dati di un file XML utilizzando un file XML Schema Definition. Le opzioni specificate vengono utilizzate per il caricamento dei dati XML. |

### Osservazioni

Per accedere ai dati del file o del flusso corrispondente durante la generazione di un report, passare un'istanza di questa classe come un'origine dati a uno dei[`ReportingEngine`](../reportingengine/) .BuildReport sovraccarichi.

Nei documenti modello, se un elemento XML di primo livello contiene solo un elenco di elementi dello stesso tipo, an`XmlDataSource` l'istanza dovrebbe essere trattata come se fosse aDataTable istanza. In caso contrario, un`XmlDataSource` l'istanza dovrebbe essere trattata come se fosse aDataRow istanza. Per ulteriori informazioni, vedere riferimento alla sintassi del modello (https://docs.aspose.com/display/wordsnet/Template+Syntax).

Quando XML Schema Definition viene passato a un costruttore di questa classe, i tipi di dati dei valori degli elementi XML semplici e degli attributi vengono determinati in base allo schema. Quindi, nei documenti modello, puoi lavorare con valori digitati anziché solo stringhe.

Quando XML Schema Definition non viene passato a un costruttore di questa classe, i tipi di dati dei valori degli elementi XML semplici e degli attributi vengono determinati automaticamente in base alle loro rappresentazioni di stringa. Quindi, nei documenti modello, puoi lavorare con valori digitati anche in questo caso. Il motore è in grado di riconoscere automaticamente i valori dei seguenti tipi:

* Nullable
* Nullable
* Nullable
* Nullable
* String

Si noti che affinché il riconoscimento automatico dei tipi di dati funzioni, le rappresentazioni di stringa dei valori di semplici elementi XML e attributi devono essere formate utilizzando impostazioni cultura invarianti.

Per ignorare il comportamento predefinito del caricamento dei dati XML, inizializzare e passare a[`XmlDataLoadOptions`](../xmldataloadoptions/) istanza a un costruttore di questa classe.

### Guarda anche

* spazio dei nomi [Aspose.Words.Reporting](../../aspose.words.reporting/)
* assemblea [Aspose.Words](../../)


