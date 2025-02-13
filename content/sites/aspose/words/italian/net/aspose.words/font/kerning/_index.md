---
title: Font.Kerning
second_title: Aspose.Words per .NET API Reference
description: Font proprietà. Ottiene o imposta la dimensione del carattere a cui inizia la crenatura.
type: docs
weight: 180
url: /it/net/aspose.words/font/kerning/
---
## Font.Kerning property

Ottiene o imposta la dimensione del carattere a cui inizia la crenatura.

```csharp
public double Kerning { get; set; }
```

### Esempi

Mostra come specificare la dimensione del carattere a cui la crenatura inizia ad avere effetto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial Black";

// Imposta la dimensione del carattere del builder e la dimensione minima alla quale la crenatura avrà effetto.
// La dimensione del carattere scende al di sotto della soglia di crenatura, quindi l'esecuzione sotto non avrà crenatura.
builder.Font.Size = 18;
builder.Font.Kerning = 24;

builder.Writeln("TALLY. (Kerning not applied)");

// Imposta la soglia di crenatura in modo che la dimensione del carattere corrente del builder sia al di sopra di essa.
// Qualsiasi testo che aggiungiamo da questo punto avrà la crenatura applicata. Gli spazi tra i caratteri
// verrà modificato, normalmente risultando in un'esecuzione del testo leggermente più gradevole dal punto di vista estetico.
builder.Font.Kerning = 12;

builder.Writeln("TALLY. (Kerning applied)");

doc.Save(ArtifactsDir + "Font.Kerning.docx");
```

### Guarda anche

* class [Font](../)
* spazio dei nomi [Aspose.Words](../../font/)
* assemblea [Aspose.Words](../../../)


