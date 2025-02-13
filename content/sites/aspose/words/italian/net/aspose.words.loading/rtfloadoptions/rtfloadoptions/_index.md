---
title: RtfLoadOptions.RtfLoadOptions
second_title: Aspose.Words per .NET API Reference
description: RtfLoadOptions costruttore. Inizializza una nuova istanza di questa classe con valori predefiniti.
type: docs
weight: 10
url: /it/net/aspose.words.loading/rtfloadoptions/rtfloadoptions/
---
## RtfLoadOptions constructor

Inizializza una nuova istanza di questa classe con valori predefiniti.

```csharp
public RtfLoadOptions()
```

### Esempi

Mostra come rilevare i caratteri UTF-8 durante il caricamento di un documento RTF.

```csharp
// Crea un oggetto "RtfLoadOptions" per modificare il modo in cui carichiamo un documento RTF.
RtfLoadOptions loadOptions = new RtfLoadOptions();

// Imposta la proprietà "RecognizeUtf8Text" su "false" per presumere che il documento utilizzi il set di caratteri ISO 8859-1
// e carica tutti i caratteri nel documento.
// Imposta la proprietà "RecognizeUtf8Text" su "true" per analizzare tutti i caratteri di lunghezza variabile che possono essere presenti nel testo.
loadOptions.RecognizeUtf8Text = recognizeUtf8Text;

Document doc = new Document(MyDir + "UTF-8 characters.rtf", loadOptions);

Assert.AreEqual(
    recognizeUtf8Text
        ? "“John Doe´s list of currency symbols”™\r" +
          "€, ¢, £, ¥, ¤"
        : "â€œJohn DoeÂ´s list of currency symbolsâ€\u009dâ„¢\r" +
          "â‚¬, Â¢, Â£, Â¥, Â¤",
    doc.FirstSection.Body.GetText().Trim());
```

### Guarda anche

* class [RtfLoadOptions](../)
* spazio dei nomi [Aspose.Words.Loading](../../rtfloadoptions/)
* assemblea [Aspose.Words](../../../)


