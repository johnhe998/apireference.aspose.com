---
title: PageSetup.FirstPageTray
second_title: Aspose.Words per .NET API Reference
description: PageSetup proprietà. Ottiene o imposta il vassoio della carta cestino da utilizzare per la prima pagina di una sezione. Il valore è specifico dellimplementazione stampante.
type: docs
weight: 130
url: /it/net/aspose.words/pagesetup/firstpagetray/
---
## PageSetup.FirstPageTray property

Ottiene o imposta il vassoio della carta (cestino) da utilizzare per la prima pagina di una sezione. Il valore è specifico dell'implementazione (stampante).

```csharp
public int FirstPageTray { get; set; }
```

### Esempi

Mostra come fare in modo che tutte le sezioni di un documento utilizzino il vassoio carta predefinito della stampante selezionata.

```csharp
Document doc = new Document();

// Trova la stampante predefinita che useremo per stampare questo documento.
// È possibile definire una stampante specifica utilizzando la proprietà "PrinterName" dell'oggetto PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// Il valore del vassoio carta memorizzato nei documenti è specifico della stampante.
// Ciò significa che il codice seguente reimposta tutti i valori del vassoio pagina per utilizzare il vassoio predefinito della stampante corrente.
// È possibile enumerare PrinterSettings.PaperSources per trovare gli altri valori validi del vassoio della carta della stampante selezionata.
foreach (Section section in doc.Sections.OfType<Section>())
{
    section.PageSetup.FirstPageTray = settings.DefaultPageSettings.PaperSource.RawKind;
    section.PageSetup.OtherPagesTray = settings.DefaultPageSettings.PaperSource.RawKind;
}
```

Mostra come impostare la stampa utilizzando diversi vassoi della stampante per diversi formati di carta.

```csharp
Document doc = new Document();

// Trova la stampante predefinita che useremo per stampare questo documento.
// È possibile definire una stampante specifica utilizzando la proprietà "PrinterName" dell'oggetto PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// Questo è il vassoio che utilizzeremo per le pagine nel formato carta "A4".
int printerTrayForA4 = settings.PaperSources[0].RawKind;

// Questo è il vassoio che useremo per le pagine nel formato carta "Lettera".
int printerTrayForLetter = settings.PaperSources[1].RawKind;

// Modifica l'oggetto PageSettings di questa sezione per fare in modo che Microsoft Word indichi la stampante
// per utilizzare uno dei vassoi che abbiamo identificato sopra, a seconda del formato carta di questa sezione.
foreach (Section section in doc.Sections.OfType<Section>())
{
    if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.Letter)
    {
        section.PageSetup.FirstPageTray = printerTrayForLetter;
        section.PageSetup.OtherPagesTray = printerTrayForLetter;
    }
    else if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.A4)
    {
        section.PageSetup.FirstPageTray = printerTrayForA4;
        section.PageSetup.OtherPagesTray = printerTrayForA4;
    }
}
```

### Guarda anche

* class [PageSetup](../)
* spazio dei nomi [Aspose.Words](../../pagesetup/)
* assemblea [Aspose.Words](../../../)


