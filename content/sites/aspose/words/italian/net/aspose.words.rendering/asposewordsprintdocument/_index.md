---
title: Class AsposeWordsPrintDocument
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Rendering.AsposeWordsPrintDocument classe. Fornisce unimplementazione predefinita per la stampa di aDocument allinterno di il framework di stampa .NET.
type: docs
weight: 4280
url: /it/net/aspose.words.rendering/asposewordsprintdocument/
---
## AsposeWordsPrintDocument class

Fornisce un'implementazione predefinita per la stampa di a[`Document`](../../aspose.words/document/) all'interno di il framework di stampa .NET.

```csharp
public class AsposeWordsPrintDocument : PrintDocument
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [AsposeWordsPrintDocument](asposewordsprintdocument/)(Document) | Inizializza una nuova istanza di questa classe. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [CachePrinterSettings](../../aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/)() | Legge e memorizza nella cache alcuni campi diPrinterSettings per ridurre i tempi di stampa. |

### Osservazioni

`AsposeWordsPrintDocument` sovrascrivePrintEventArgs) per stampare l'intervallo di pagine specificato inPrinterSettings.

Un singolo documento Word può essere costituito da più sezioni che specificano pagine con dimensioni diverse, orientamento e vassoi carta.`AsposeWordsPrintDocument` sostituzioni QueryPageSettingsEventArgs) per selezionare correttamente il formato carta, l'orientamento e l'origine carta durante la stampa di un documento Word.

Microsoft Word memorizza i valori specifici della stampante per i vassoi carta in un documento Word e, pertanto, stampando solo sullo stesso modello di stampante di quello selezionato quando l'utente ha specificato i vassoi carta risulterà nella stampa dai vassoi corretti. Se si stampa un documento su una stampante diversa, molto probabilmente verrà utilizzato il vassoio carta predefinito, non i vassoi specificati nel documento.

### Guarda anche

* spazio dei nomi [Aspose.Words.Rendering](../../aspose.words.rendering/)
* assemblea [Aspose.Words](../../)


