---
title: CompareOptions.IgnoreDmlUniqueId
second_title: Aspose.Words per .NET API Reference
description: CompareOptions proprietà. Specifica se ignorare la differenza nellID univoco di DrawingML. Il valore predefinito è falso .
type: docs
weight: 50
url: /it/net/aspose.words.comparing/compareoptions/ignoredmluniqueid/
---
## CompareOptions.IgnoreDmlUniqueId property

Specifica se ignorare la differenza nell'ID univoco di DrawingML. Il valore predefinito è **falso** .

```csharp
public bool IgnoreDmlUniqueId { get; set; }
```

### Esempi

Mostra come confrontare i documenti ignorando l'ID univoco DML.

```csharp
Document docA = new Document(MyDir + "DML unique ID original.docx");
Document docB = new Document(MyDir + "DML unique ID compare.docx");

// Per impostazione predefinita, Aspose.Words non ignora l'ID univoco di DML e il conteggio delle revisioni era 2.
// Se stiamo ignorando l'ID univoco di DML e il conteggio delle revisioni era 0.
Aspose.Words.Comparing.CompareOptions compareOptions = new Aspose.Words.Comparing.CompareOptions();
compareOptions.IgnoreDmlUniqueId = isIgnoreDmlUniqueId;

docA.Compare(docB, "Aspose.Words", DateTime.Now, compareOptions);

Assert.AreEqual(isIgnoreDmlUniqueId ? 0 : 2, docA.Revisions.Count);
```

### Guarda anche

* class [CompareOptions](../)
* spazio dei nomi [Aspose.Words.Comparing](../../compareoptions/)
* assemblea [Aspose.Words](../../../)


