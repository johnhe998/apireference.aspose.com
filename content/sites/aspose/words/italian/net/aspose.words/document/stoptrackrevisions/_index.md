---
title: Document.StopTrackRevisions
second_title: Aspose.Words per .NET API Reference
description: Document metodo. Arresta la marcatura automatica delle modifiche al documento come revisioni.
type: docs
weight: 700
url: /it/net/aspose.words/document/stoptrackrevisions/
---
## Document.StopTrackRevisions method

Arresta la marcatura automatica delle modifiche al documento come revisioni.

```csharp
public void StopTrackRevisions()
```

### Esempi

Mostra come tenere traccia delle revisioni durante la modifica di un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// La modifica di un documento di solito non conta come revisione finché non iniziamo a seguirli.
builder.Write("Hello world! ");

Assert.AreEqual(0, doc.Revisions.Count);
Assert.False(doc.FirstSection.Body.Paragraphs[0].Runs[0].IsInsertRevision);

doc.StartTrackRevisions("John Doe");

builder.Write("Hello again! ");

Assert.AreEqual(1, doc.Revisions.Count);
Assert.True(doc.FirstSection.Body.Paragraphs[0].Runs[1].IsInsertRevision);
Assert.AreEqual("John Doe", doc.Revisions[0].Author);
Assert.That(doc.Revisions[0].DateTime, Is.EqualTo(DateTime.Now).Within(10).Milliseconds);

// Interrompi il monitoraggio delle revisioni per non contare le modifiche future come revisioni.
doc.StopTrackRevisions();
builder.Write("Hello again! ");

Assert.AreEqual(1, doc.Revisions.Count);
Assert.False(doc.FirstSection.Body.Paragraphs[0].Runs[2].IsInsertRevision);

// La creazione di revisioni fornisce loro una data e un'ora dell'operazione.
// Possiamo disabilitarlo passando DateTime.MinValue quando iniziamo a tenere traccia delle revisioni.
doc.StartTrackRevisions("John Doe", DateTime.MinValue);
builder.Write("Hello again! ");

Assert.AreEqual(2, doc.Revisions.Count);
Assert.AreEqual("John Doe", doc.Revisions[1].Author);
Assert.AreEqual(DateTime.MinValue, doc.Revisions[1].DateTime);

// Possiamo accettare/rifiutare queste revisioni a livello di codice
// chiamando metodi come Document.AcceptAllRevisions o il metodo Accept di ogni revisione.
// In Microsoft Word, possiamo elaborarli manualmente tramite "Revisione" -> "I cambiamenti".
doc.Save(ArtifactsDir + "Document.StartTrackRevisions.docx");
```

### Guarda anche

* method [StartTrackRevisions](../starttrackrevisions/)
* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


