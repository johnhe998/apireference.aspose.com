---
title: Font.LocaleId
second_title: Aspose.Words per .NET API Reference
description: Font proprietà. Ottiene o imposta lidentificatore locale lingua dei caratteri formattati.
type: docs
weight: 200
url: /it/net/aspose.words/font/localeid/
---
## Font.LocaleId property

Ottiene o imposta l'identificatore locale (lingua) dei caratteri formattati.

```csharp
public int LocaleId { get; set; }
```

### Osservazioni

Per l'elenco degli identificatori di locale, vedere https://msdn.microsoft.com/en-us/library/cc233965.aspx

### Esempi

Mostra come impostare la localizzazione del testo che stiamo aggiungendo con un generatore di documenti.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Se impostiamo la lingua del carattere su inglese e inseriamo del testo russo,
// il correttore ortografico della lingua inglese non riconoscerà il testo e lo rileverà come un errore di ortografia.
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;
builder.Writeln("Привет!");

// Imposta una lingua corrispondente per il testo che stiamo per aggiungere per applicare il correttore ortografico appropriato.
builder.Font.LocaleId = new CultureInfo("ru-RU", false).LCID;
builder.Writeln("Привет!");

doc.Save(ArtifactsDir + "Font.LocaleId.docx");
```

### Guarda anche

* class [Font](../)
* spazio dei nomi [Aspose.Words](../../font/)
* assemblea [Aspose.Words](../../../)


