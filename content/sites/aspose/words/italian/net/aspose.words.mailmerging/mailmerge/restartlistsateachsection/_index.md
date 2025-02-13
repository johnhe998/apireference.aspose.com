---
title: MailMerge.RestartListsAtEachSection
second_title: Aspose.Words per .NET API Reference
description: MailMerge proprietà. Ottiene o imposta un valore che indica se gli elenchi vengono riavviati in ciascuna sezione dopo lesecuzione di una stampa unione.
type: docs
weight: 110
url: /it/net/aspose.words.mailmerging/mailmerge/restartlistsateachsection/
---
## MailMerge.RestartListsAtEachSection property

Ottiene o imposta un valore che indica se gli elenchi vengono riavviati in ciascuna sezione dopo l'esecuzione di una stampa unione.

```csharp
public bool RestartListsAtEachSection { get; set; }
```

### Osservazioni

Il valore predefinito è **VERO** .

### Esempi

Mostra come controllare se la numerazione degli elenchi viene riavviata o meno in ciascuna sezione quando viene eseguita la stampa unione.

```csharp
Document doc = new Document(MyDir + "Section breaks with numbering.docx");

doc.MailMerge.RestartListsAtEachSection = false;
doc.MailMerge.Execute(new string[0], new object[0]);

doc.Save(ArtifactsDir + "MailMerge.RestartListsAtEachSection.pdf");
```

### Guarda anche

* class [MailMerge](../)
* spazio dei nomi [Aspose.Words.MailMerging](../../mailmerge/)
* assemblea [Aspose.Words](../../../)


