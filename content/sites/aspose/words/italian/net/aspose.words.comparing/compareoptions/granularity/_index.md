---
title: CompareOptions.Granularity
second_title: Aspose.Words per .NET API Reference
description: CompareOptions proprietà. Specifica se le modifiche vengono tracciate per carattere o per parola. Il valore predefinito èWordLevel .
type: docs
weight: 20
url: /it/net/aspose.words.comparing/compareoptions/granularity/
---
## CompareOptions.Granularity property

Specifica se le modifiche vengono tracciate per carattere o per parola. Il valore predefinito èWordLevel .

```csharp
public Granularity Granularity { get; set; }
```

### Esempi

Mostra per specificare una granularità durante il confronto dei documenti.

```csharp
Document docA = new Document();
DocumentBuilder builderA = new DocumentBuilder(docA);
builderA.Writeln("Alpha Lorem ipsum dolor sit amet, consectetur adipiscing elit");

Document docB = new Document();
DocumentBuilder builderB = new DocumentBuilder(docB);
builderB.Writeln("Lorems ipsum dolor sit amet consectetur - \"adipiscing\" elit");

// Specifica se le modifiche stanno tenendo traccia
// per carattere ("Granularity.CharLevel") o per parola ("Granularity.WordLevel").
Aspose.Words.Comparing.CompareOptions compareOptions = new Aspose.Words.Comparing.CompareOptions();
compareOptions.Granularity = granularity;

docA.Compare(docB, "author", DateTime.Now, compareOptions);

// La raccolta di gruppi di revisione del primo documento contiene tutte le differenze tra i documenti.
RevisionGroupCollection groups = docA.Revisions.Groups;
Assert.AreEqual(5, groups.Count);
```

### Guarda anche

* enum [Granularity](../../granularity/)
* class [CompareOptions](../)
* spazio dei nomi [Aspose.Words.Comparing](../../compareoptions/)
* assemblea [Aspose.Words](../../../)


