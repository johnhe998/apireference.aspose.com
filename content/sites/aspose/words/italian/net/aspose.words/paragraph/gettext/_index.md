---
title: Paragraph.GetText
second_title: Aspose.Words per .NET API Reference
description: Paragraph metodo. Ottiene il testo di questo paragrafo incluso il carattere di fine paragrafo.
type: docs
weight: 260
url: /it/net/aspose.words/paragraph/gettext/
---
## Paragraph.GetText method

Ottiene il testo di questo paragrafo incluso il carattere di fine paragrafo.

```csharp
public override string GetText()
```

### Osservazioni

Il testo di tutti i nodi figlio viene concatenato e il carattere di fine paragrafo viene aggiunto come segue:

* Se il paragrafo è l'ultimo paragrafo di[`Body`](../../body/) , quindi [`ControlChar.SectionBreak`](../../controlchar/sectionbreak/) (\x000c) viene aggiunto.
* Se il paragrafo è l'ultimo paragrafo di[`Cell`](../../../aspose.words.tables/cell/) , quindi [`ControlChar.Cell`](../../controlchar/cell/) (\x0007) viene aggiunto.
* Per tutti gli altri paragrafi [`ControlChar.ParagraphBreak`](../../controlchar/paragraphbreak/) (\r) viene aggiunto.

La stringa restituita include tutti i caratteri di controllo e speciali come descritto in[`ControlChar`](../../controlchar/).

### Esempi

Mostra come aggiungere, aggiornare ed eliminare nodi figlio in una raccolta di figli di CompositeNode.

```csharp
Document doc = new Document();

// Un documento vuoto, per impostazione predefinita, ha un paragrafo.
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);

// I nodi compositi come il nostro paragrafo possono contenere altri nodi compositi e inline come figli.
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Run paragraphText = new Run(doc, "Initial text. ");
paragraph.AppendChild(paragraphText);

// Crea altri tre nodi di esecuzione.
Run run1 = new Run(doc, "Run 1. ");
Run run2 = new Run(doc, "Run 2. ");
Run run3 = new Run(doc, "Run 3. ");

// Il corpo del documento non visualizzerà queste esecuzioni finché non le inseriamo in un nodo composito
// che di per sé fa parte dell'albero dei nodi del documento, come abbiamo fatto con la prima esecuzione.
// Possiamo determinare dove si trova il contenuto del testo dei nodi che inseriamo
// appare nel documento specificando una posizione di inserimento relativa a un altro nodo nel paragrafo.
Assert.AreEqual("Initial text.", paragraph.GetText().Trim());

// Inserisce la seconda sequenza nel paragrafo prima della sequenza iniziale.
paragraph.InsertBefore(run2, paragraphText);

Assert.AreEqual("Run 2. Initial text.", paragraph.GetText().Trim());

// Inserisce la terza esecuzione dopo l'esecuzione iniziale.
paragraph.InsertAfter(run3, paragraphText);

Assert.AreEqual("Run 2. Initial text. Run 3.", paragraph.GetText().Trim());

// Inserisce la prima esecuzione all'inizio della raccolta di nodi figlio del paragrafo.
paragraph.PrependChild(run1);

Assert.AreEqual("Run 1. Run 2. Initial text. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(4, paragraph.GetChildNodes(NodeType.Any, true).Count);

// Possiamo modificare il contenuto della corsa modificando ed eliminando i nodi figlio esistenti.
((Run)paragraph.GetChildNodes(NodeType.Run, true)[1]).Text = "Updated run 2. ";
paragraph.GetChildNodes(NodeType.Run, true).Remove(paragraphText);

Assert.AreEqual("Run 1. Updated run 2. Run 3.", paragraph.GetText().Trim());
Assert.AreEqual(3, paragraph.GetChildNodes(NodeType.Any, true).Count);
```

### Guarda anche

* class [Paragraph](../)
* spazio dei nomi [Aspose.Words](../../paragraph/)
* assemblea [Aspose.Words](../../../)


