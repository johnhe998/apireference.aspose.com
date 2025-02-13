---
title: Font.ComplexScript
second_title: Aspose.Words per .NET API Reference
description: Font proprietà. Specifica se il contenuto di questa esecuzione deve essere trattato come testo di script complesso indipendentemente dai valori dei caratteri Unicode durante la determinazione della formattazione per questa esecuzione.
type: docs
weight: 80
url: /it/net/aspose.words/font/complexscript/
---
## Font.ComplexScript property

Specifica se il contenuto di questa esecuzione deve essere trattato come testo di script complesso indipendentemente dai valori dei caratteri Unicode durante la determinazione della formattazione per questa esecuzione.

```csharp
public bool ComplexScript { get; set; }
```

### Esempi

Mostra come aggiungere testo che viene sempre trattato come script complesso.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.ComplexScript = true;

builder.Writeln("Text treated as complex script.");

doc.Save(ArtifactsDir + "Font.ComplexScript.docx");
```

### Guarda anche

* class [Font](../)
* spazio dei nomi [Aspose.Words](../../font/)
* assemblea [Aspose.Words](../../../)


