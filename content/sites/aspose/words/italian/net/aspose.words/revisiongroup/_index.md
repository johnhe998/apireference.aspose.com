---
title: Class RevisionGroup
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.RevisionGroup classe. Rappresenta un gruppo di sequenzialiRevision oggetti.
type: docs
weight: 4520
url: /it/net/aspose.words/revisiongroup/
---
## RevisionGroup class

Rappresenta un gruppo di sequenziali[`Revision`](../revision/) oggetti.

```csharp
public class RevisionGroup
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Author](../../aspose.words/revisiongroup/author/) { get; } | Ottiene l'autore di questo gruppo di revisioni. |
| [RevisionType](../../aspose.words/revisiongroup/revisiontype/) { get; } | Ottiene il tipo di revisioni incluse in questo gruppo. |
| [Text](../../aspose.words/revisiongroup/text/) { get; } | Restituisce il testo inserito/cancellato/spostato o la descrizione del cambio formato. |

### Esempi

Mostra come stampare le informazioni su un gruppo di revisioni in un documento.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

Assert.AreEqual(7, doc.Revisions.Groups.Count);

foreach (RevisionGroup group in doc.Revisions.Groups)
{
    Console.WriteLine(
        $"Revision author: {group.Author}; Revision type: {group.RevisionType} \n\tRevision text: {group.Text}");
}
```

### Guarda anche

* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


