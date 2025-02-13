---
title: DocumentBuilder.MoveToParagraph
second_title: Aspose.Words per .NET API Reference
description: DocumentBuilder metodo. Sposta il cursore su un paragrafo nella sezione corrente.
type: docs
weight: 540
url: /it/net/aspose.words/documentbuilder/movetoparagraph/
---
## DocumentBuilder.MoveToParagraph method

Sposta il cursore su un paragrafo nella sezione corrente.

```csharp
public void MoveToParagraph(int paragraphIndex, int characterIndex)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| paragraphIndex | Int32 | Indice del paragrafo in cui spostarsi. |
| characterIndex | Int32 | L'indice del carattere all'interno del paragrafo. Un valore negativo consente di specificare una posizione dalla fine del paragrafo. Utilizzare -1 per spostarsi alla fine di il paragrafo. |

### Osservazioni

La navigazione viene eseguita all'interno della storia corrente della sezione corrente. Cioè, se hai spostato il cursore sull'intestazione principale della prima sezione, allora paragrafoIndice ha specificato l'indice del paragrafo all'interno di quell'intestazione di quella sezione.

Quando index è maggiore o uguale a 0, specifica un indice da all'inizio della sezione con 0 come primo paragrafo. Quando l'indice del paragrafo è inferiore a 0, , ha specificato un indice dalla fine della sezione con -1 come ultimo paragrafo.

### Esempi

Mostra come spostare la posizione del cursore di un builder su un paragrafo specifico.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(22, paragraphs.Count);

// Crea un generatore di documenti per modificare il documento. Il cursore del costruttore,
// che è il punto in cui inserirà nuovi nodi quando chiamiamo i suoi metodi di costruzione del documento,
// è attualmente all'inizio del documento.
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Spostare il cursore su un paragrafo diverso posizionerà il cursore davanti a quel paragrafo.
builder.MoveToParagraph(2, 0);
// Qualsiasi nuovo contenuto che aggiungiamo verrà inserito a quel punto.
builder.Writeln("This is a new third paragraph. ");
```

### Guarda anche

* class [DocumentBuilder](../)
* spazio dei nomi [Aspose.Words](../../documentbuilder/)
* assemblea [Aspose.Words](../../../)


