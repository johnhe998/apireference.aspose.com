---
title: Paragraph.IsMoveFromRevision
second_title: Aspose.Words per .NET API Reference
description: Paragraph proprietà. Restituisce VERO se questo oggetto è stato spostato eliminato in Microsoft Word mentre era abilitato il rilevamento delle modifiche.
type: docs
weight: 130
url: /it/net/aspose.words/paragraph/ismovefromrevision/
---
## Paragraph.IsMoveFromRevision property

Restituisce **VERO** se questo oggetto è stato spostato (eliminato) in Microsoft Word mentre era abilitato il rilevamento delle modifiche.

```csharp
public bool IsMoveFromRevision { get; }
```

### Esempi

Mostra come verificare se un paragrafo è una revisione di spostamento.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Questo documento contiene le revisioni "Sposta", che appaiono quando si evidenzia il testo con il cursore,
// e quindi trascinalo per spostarlo in un'altra posizione
// durante il monitoraggio delle revisioni in Microsoft Word tramite "Revisione" -> "Tenere traccia delle modifiche".
Assert.AreEqual(6, doc.Revisions.Count(r => r.RevisionType == RevisionType.Moving));

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

// Le revisioni di spostamento sono costituite da coppie di revisioni "Sposta da" e "Sposta in". 
// Queste revisioni sono potenziali modifiche al documento che possiamo accettare o rifiutare.
// Prima di accettare/rifiutare una revisione di spostamento, il documento
// deve tenere traccia sia della destinazione di partenza che di quella di arrivo del testo.
// Il secondo e il quarto paragrafo definiscono una di queste revisioni, e quindi entrambi hanno lo stesso contenuto.
Assert.AreEqual(paragraphs[1].GetText(), paragraphs[3].GetText());

// La revisione "Sposta da" è il paragrafo da cui abbiamo trascinato il testo.
// Se accettiamo la revisione, questo paragrafo scomparirà,
// e l'altro rimarranno e non saranno più una revisione.
Assert.True(paragraphs[1].IsMoveFromRevision);

// La revisione "Sposta in" è il paragrafo in cui abbiamo trascinato il testo.
// Se rifiutiamo la revisione, questo paragrafo scomparirà e l'altro rimarrà.
Assert.True(paragraphs[3].IsMoveToRevision);
```

### Guarda anche

* class [Paragraph](../)
* spazio dei nomi [Aspose.Words](../../paragraph/)
* assemblea [Aspose.Words](../../../)


