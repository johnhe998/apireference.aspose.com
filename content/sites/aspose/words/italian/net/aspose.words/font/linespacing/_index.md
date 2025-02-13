---
title: Font.LineSpacing
second_title: Aspose.Words per .NET API Reference
description: Font proprietà. Restituisce linterlinea di questo font in punti.
type: docs
weight: 190
url: /it/net/aspose.words/font/linespacing/
---
## Font.LineSpacing property

Restituisce l'interlinea di questo font (in punti).

```csharp
public double LineSpacing { get; }
```

### Esempi

Mostra come ottenere l'interlinea di un font, in punti.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Imposta caratteri diversi per DocumentBuilder e verifica l'interlinea.
builder.Font.Name = "Calibri";
Assert.AreEqual(14.6484375d, builder.Font.LineSpacing);

builder.Font.Name = "Times New Roman";
Assert.AreEqual(13.798828125d, builder.Font.LineSpacing);
```

### Guarda anche

* class [Font](../)
* spazio dei nomi [Aspose.Words](../../font/)
* assemblea [Aspose.Words](../../../)


