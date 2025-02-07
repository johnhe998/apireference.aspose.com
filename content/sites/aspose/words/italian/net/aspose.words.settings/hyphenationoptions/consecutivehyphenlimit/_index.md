---
title: HyphenationOptions.ConsecutiveHyphenLimit
second_title: Aspose.Words per .NET API Reference
description: HyphenationOptions proprietà. Ottiene o imposta il numero massimo di righe consecutive che possono terminare con trattini. Il valore predefinito per questa proprietà è 0.
type: docs
weight: 30
url: /it/net/aspose.words.settings/hyphenationoptions/consecutivehyphenlimit/
---
## HyphenationOptions.ConsecutiveHyphenLimit property

Ottiene o imposta il numero massimo di righe consecutive che possono terminare con trattini. Il valore predefinito per questa proprietà è 0.

```csharp
public int ConsecutiveHyphenLimit { get; set; }
```

### Osservazioni

Se il valore di questa proprietà è impostato su 0, qualsiasi numero di righe consecutive può terminare con trattini.

La proprietà non ha effetto durante il salvataggio in formati di pagina fissi, ad es. PDF.

### Esempi

Mostra come configurare la sillabazione automatica.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.HyphenationOptions.AutoHyphenation = true;
doc.HyphenationOptions.ConsecutiveHyphenLimit = 2;
doc.HyphenationOptions.HyphenationZone = 720;
doc.HyphenationOptions.HyphenateCaps = true;

doc.Save(ArtifactsDir + "Document.HyphenationOptions.docx");
```

### Guarda anche

* class [HyphenationOptions](../)
* spazio dei nomi [Aspose.Words.Settings](../../hyphenationoptions/)
* assemblea [Aspose.Words](../../../)


