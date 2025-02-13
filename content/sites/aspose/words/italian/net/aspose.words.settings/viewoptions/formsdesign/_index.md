---
title: ViewOptions.FormsDesign
second_title: Aspose.Words per .NET API Reference
description: ViewOptions proprietà. Specifica se il documento è in modalità progettazione moduli.
type: docs
weight: 30
url: /it/net/aspose.words.settings/viewoptions/formsdesign/
---
## ViewOptions.FormsDesign property

Specifica se il documento è in modalità progettazione moduli.

```csharp
public bool FormsDesign { get; set; }
```

### Osservazioni

Attualmente funziona solo per documenti in formato WordML.

### Esempi

Mostra come abilitare/disabilitare la modalità di progettazione dei moduli.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Imposta la proprietà "FormsDesign" su "false" per mantenere la modalità di progettazione dei moduli disabilitata.
// Imposta la proprietà "FormsDesign" su "true" per abilitare la modalità di progettazione dei moduli.
doc.ViewOptions.FormsDesign = useFormsDesign;

doc.Save(ArtifactsDir + "ViewOptions.FormsDesign.xml");

Assert.AreEqual(useFormsDesign,
    File.ReadAllText(ArtifactsDir + "ViewOptions.FormsDesign.xml").Contains("<w:formsDesign />"));
```

### Guarda anche

* class [ViewOptions](../)
* spazio dei nomi [Aspose.Words.Settings](../../viewoptions/)
* assemblea [Aspose.Words](../../../)


