---
title: ListLevel.CustomNumberStyleFormat
second_title: Aspose.Words per .NET API Reference
description: ListLevel proprietà. Ottiene il formato dello stile numerico personalizzato per questo livello di elenco. Ad esempio a ç ĝ ....
type: docs
weight: 20
url: /it/net/aspose.words.lists/listlevel/customnumberstyleformat/
---
## ListLevel.CustomNumberStyleFormat property

Ottiene il formato dello stile numerico personalizzato per questo livello di elenco. Ad esempio: "a, ç, ĝ, ...".

```csharp
public string CustomNumberStyleFormat { get; }
```

### Esempi

Mostra come ottenere il formato per un elenco con lo stile numerico personalizzato.

```csharp
Document doc = new Document(MyDir + "List with leading zero.docx");

ListLevel listLevel = doc.FirstSection.Body.Paragraphs[0].ListFormat.ListLevel;

string customNumberStyleFormat = string.Empty;

if (listLevel.NumberStyle == NumberStyle.Custom)
    customNumberStyleFormat = listLevel.CustomNumberStyleFormat;

Assert.AreEqual("001, 002, 003, ...", customNumberStyleFormat);

// Possiamo ottenere il valore per l'indice specificato dell'elemento dell'elenco.
Assert.AreEqual("iv", ListLevel.GetEffectiveValue(4, NumberStyle.LowercaseRoman, null));
Assert.AreEqual("005", ListLevel.GetEffectiveValue(5, NumberStyle.Custom, customNumberStyleFormat));
```

### Guarda anche

* class [ListLevel](../)
* spazio dei nomi [Aspose.Words.Lists](../../listlevel/)
* assemblea [Aspose.Words](../../../)


