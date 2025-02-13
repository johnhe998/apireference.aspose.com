---
title: Font.AllCaps
second_title: Aspose.Words per .NET API Reference
description: Font proprietà. Vero se il carattere è formattato come tutte le lettere maiuscole.
type: docs
weight: 10
url: /it/net/aspose.words/font/allcaps/
---
## Font.AllCaps property

Vero se il carattere è formattato come tutte le lettere maiuscole.

```csharp
public bool AllCaps { get; set; }
```

### Esempi

Mostra come formattare una corsa per visualizzarne il contenuto in maiuscolo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// Ci sono due modi per far sì che una corsa visualizzi il testo minuscolo in maiuscolo senza modificare il contenuto.
// 1 - Imposta il flag AllCaps per visualizzare tutti i caratteri in maiuscolo regolare:
Run run = new Run(doc, "all capitals");
run.Font.AllCaps = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

// 2 - Imposta il flag SmallCaps per visualizzare tutti i caratteri in maiuscolo:
// Se un carattere è minuscolo, apparirà nella sua forma maiuscola
// ma avrà la stessa altezza delle lettere minuscole (l'altezza x del carattere).
// I caratteri che erano originariamente in maiuscolo avranno lo stesso aspetto.
run = new Run(doc, "Small Capitals");
run.Font.SmallCaps = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.Caps.docx");
```

### Guarda anche

* class [Font](../)
* spazio dei nomi [Aspose.Words](../../font/)
* assemblea [Aspose.Words](../../../)


