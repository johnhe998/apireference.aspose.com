---
title: Run.Run
second_title: Aspose.Words per .NET API Reference
description: Run costruttore. Inizializza una nuova istanza di Correre classe.
type: docs
weight: 10
url: /it/net/aspose.words/run/run/
---
## Run(DocumentBase) {#constructor}

Inizializza una nuova istanza di **Correre** classe.

```csharp
public Run(DocumentBase doc)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| doc | DocumentBase | Il documento del proprietario. |

### Osservazioni

quando **Correre** viene creato, appartiene al documento specificato, ma non fa ancora parte del documento e **ParentNode** è zero.

Aggiungere **Correre** al documento utilizzare InsertAfter o InsertBefore nel paragrafo in cui si desidera inserire la sequenza.

### Esempi

Mostra come costruire manualmente un documento Aspose.Words.

```csharp
Document doc = new Document();

// Un documento vuoto contiene una sezione, un corpo e un paragrafo.
// Chiama il metodo "RemoveAllChildren" per rimuovere tutti quei nodi,
// e finisci con un nodo documento senza figli.
doc.RemoveAllChildren();

// Questo documento ora non ha nodi figlio compositi a cui possiamo aggiungere contenuto.
// Se desideriamo modificarlo, dovremo ripopolare la sua raccolta di nodi.
// Innanzitutto, crea una nuova sezione, quindi aggiungila come figlio al nodo del documento radice.
Section section = new Section(doc);
doc.AppendChild(section);

// Imposta alcune proprietà di impostazione della pagina per la sezione.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// Una sezione ha bisogno di un corpo, che conterrà e visualizzerà tutto il suo contenuto
// nella pagina tra l'intestazione e il piè di pagina della sezione.
Body body = new Body(doc);
section.AppendChild(body);

// Crea un paragrafo, imposta alcune proprietà di formattazione e quindi aggiungilo come figlio al corpo.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// Infine, aggiungi del contenuto per fare il documento. Crea una corsa,
// imposta l'aspetto e il contenuto, quindi aggiungilo come figlio al paragrafo.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### Guarda anche

* class [DocumentBase](../../documentbase/)
* class [Run](../)
* spazio dei nomi [Aspose.Words](../../run/)
* assemblea [Aspose.Words](../../../)

---

## Run(DocumentBase, string) {#constructor_1}

Inizializza una nuova istanza di **Correre** classe.

```csharp
public Run(DocumentBase doc, string text)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| doc | DocumentBase | Il documento del proprietario. |
| text | String | Il testo della corsa. |

### Osservazioni

quando **Correre** viene creato, appartiene al documento specificato, ma non fa ancora parte del documento e **ParentNode** è zero.

Aggiungere **Correre** al documento utilizzare InsertAfter o InsertBefore nel paragrafo in cui si desidera inserire la sequenza.

### Esempi

Mostra come formattare una sequenza di testo utilizzando la relativa proprietà del carattere.

```csharp
Document doc = new Document();
Run run = new Run(doc, "Hello world!");

Aspose.Words.Font font = run.Font;
font.Name = "Courier New";
font.Size = 36;
font.HighlightColor = Color.Yellow;

doc.FirstSection.Body.FirstParagraph.AppendChild(run);
doc.Save(ArtifactsDir + "Font.CreateFormattedRun.docx");
```

### Guarda anche

* class [DocumentBase](../../documentbase/)
* class [Run](../)
* spazio dei nomi [Aspose.Words](../../run/)
* assemblea [Aspose.Words](../../../)


