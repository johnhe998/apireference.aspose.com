---
title: HyphenationOptions.AutoHyphenation
second_title: Aspose.Words per .NET API Reference
description: HyphenationOptions proprietà. Ottiene o imposta il valore che determina se la sillabazione automatica è attivata per il documento. Il valore predefinito per questa proprietà è falso .
type: docs
weight: 20
url: /it/net/aspose.words.settings/hyphenationoptions/autohyphenation/
---
## HyphenationOptions.AutoHyphenation property

Ottiene o imposta il valore che determina se la sillabazione automatica è attivata per il documento. Il valore predefinito per questa proprietà è **falso** .

```csharp
public bool AutoHyphenation { get; set; }
```

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


