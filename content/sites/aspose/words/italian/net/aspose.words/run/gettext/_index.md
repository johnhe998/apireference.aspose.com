---
title: Run.GetText
second_title: Aspose.Words per .NET API Reference
description: Run metodo. Ottiene il testo della corsa.
type: docs
weight: 50
url: /it/net/aspose.words/run/gettext/
---
## Run.GetText method

Ottiene il testo della corsa.

```csharp
public override string GetText()
```

### Valore di ritorno

Il testo della corsa.

### Esempi

Mostra come stampare la struttura del nodo di ogni intestazione e piè di pagina in un documento.

```csharp
public void HeaderFooterToText()
{
    Document doc = new Document(MyDir + "DocumentVisitor-compatible features.docx");
    HeaderFooterStructurePrinter visitor = new HeaderFooterStructurePrinter();

    // Quando otteniamo un nodo composito per accettare un visitatore del documento, il visitatore visita il nodo di accettazione,
    // e quindi attraversa tutti i figli del nodo in modo approfondito.
    // Il visitatore può leggere e modificare ogni nodo visitato.
    doc.Accept(visitor);

    Console.WriteLine(visitor.GetText());

    // Un modo alternativo per accedere all'intestazione/piè di pagina di un documento sezione per sezione consiste nell'accedere alla raccolta.
    HeaderFooter[] headerFooters = doc.FirstSection.HeadersFooters.ToArray();
    Assert.AreEqual(3, headerFooters.Length);
}

/// <summary>
/// Attraversa l'albero non binario di nodi figlio di un nodo.
/// Crea una mappa sotto forma di una stringa di tutti i nodi HeaderFooter incontrati e dei loro figli.
/// </summary>
public class HeaderFooterStructurePrinter : DocumentVisitor
{
    public HeaderFooterStructurePrinter()
    {
        mBuilder = new StringBuilder();
        mVisitorIsInsideHeaderFooter = false;
    }

    public string GetText()
    {
        return mBuilder.ToString();
    }

    /// <summary>
    /// Chiamato quando viene rilevato un nodo Run nel documento.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        if (mVisitorIsInsideHeaderFooter) IndentAndAppendLine("[Run] \"" + run.GetText() + "\"");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Chiamato quando viene rilevato un nodo HeaderFooter nel documento.
    /// </summary>
    public override VisitorAction VisitHeaderFooterStart(HeaderFooter headerFooter)
    {
        IndentAndAppendLine("[HeaderFooter start] HeaderFooterType: " + headerFooter.HeaderFooterType);
        mDocTraversalDepth++;
        mVisitorIsInsideHeaderFooter = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Chiamato dopo che tutti i nodi figlio di un nodo HeaderFooter sono stati visitati.
    /// </summary>
    public override VisitorAction VisitHeaderFooterEnd(HeaderFooter headerFooter)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[HeaderFooter end]");
        mVisitorIsInsideHeaderFooter = false;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Aggiunge una riga allo StringBuilder e la indenta in base alla profondità del visitatore nell'albero del documento.
    /// </summary>
    /// <nome parametro="testo"></param>
    private void IndentAndAppendLine(string text)
    {
        for (int i = 0; i < mDocTraversalDepth; i++) mBuilder.Append("|  ");

        mBuilder.AppendLine(text);
    }

    private bool mVisitorIsInsideHeaderFooter;
    private int mDocTraversalDepth;
    private readonly StringBuilder mBuilder;
}
```

### Guarda anche

* class [Run](../)
* spazio dei nomi [Aspose.Words](../../run/)
* assemblea [Aspose.Words](../../../)


