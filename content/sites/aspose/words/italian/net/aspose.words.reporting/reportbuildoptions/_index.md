---
title: Enum ReportBuildOptions
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Reporting.ReportBuildOptions enum. Specifica le opzioni che controllano il comportamento diReportingEngine durante la creazione di un rapporto.
type: docs
weight: 4460
url: /it/net/aspose.words.reporting/reportbuildoptions/
---
## ReportBuildOptions enumeration

Specifica le opzioni che controllano il comportamento di[`ReportingEngine`](../reportingengine/) durante la creazione di un rapporto.

```csharp
[Flags]
public enum ReportBuildOptions
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Specifica le opzioni predefinite. |
| AllowMissingMembers | `1` | Specifica che i membri dell'oggetto mancanti devono essere trattati come valori letterali null dal motore. Questa opzione ha effetto solo sull'accesso ai membri dell'oggetto istanza (ovvero non statici) e ai metodi di estensione. Se questa opzione non è impostata, il motore genera un'eccezione quando rileva un membro dell'oggetto mancante. |
| RemoveEmptyParagraphs | `2` | Specifica che il motore deve rimuovere i paragrafi che diventano vuoti dopo che i tag della sintassi del modello sono stati rimossi o sostituiti con valori vuoti. |
| InlineErrorMessages | `4` | Specifica che il motore deve incorporare i messaggi di errore della sintassi del modello nei documenti di output. Se questa opzione non è impostata, il motore genera un'eccezione quando rileva un errore di sintassi. |
| UseLegacyHeaderFooterVisiting | `8` | Specifica che il motore deve visitare i nodi figlio della sezione (intestazioni, piè di pagina, corpi) in un ordine compatibile con le versioni di Aspose.Words precedenti alla 21.9. |
| RespectJpegExifOrientation | `10` | Specifica che il motore deve utilizzare i valori di orientamento dell'immagine EXIF ​​​​per ruotare in modo appropriato le immagini JPEG inserite . |

### Guarda anche

* spazio dei nomi [Aspose.Words.Reporting](../../aspose.words.reporting/)
* assemblea [Aspose.Words](../../)


