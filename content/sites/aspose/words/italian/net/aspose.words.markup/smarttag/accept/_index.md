---
title: SmartTag.Accept
second_title: Aspose.Words per .NET API Reference
description: SmartTag metodo. Accetta un visitatore.
type: docs
weight: 60
url: /it/net/aspose.words.markup/smarttag/accept/
---
## SmartTag.Accept method

Accetta un visitatore.

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| visitor | DocumentVisitor | Il visitatore che visiterà i nodi. |

### Valore di ritorno

Vero se tutti i nodi sono stati visitati; false se DocumentVisitor ha interrotto l'operazione prima di visitare tutti i nodi.

### Osservazioni

Enumera su questo nodo e tutti i suoi figli. Ogni nodo chiama un metodo corrispondente su DocumentVisitor.

Per ulteriori informazioni, vedere il modello di progettazione del visitatore.

Chiamate[`VisitSmartTagStart`](../../../aspose.words/documentvisitor/visitsmarttagstart/) , quindi chiama[`Accept`](../../../aspose.words/node/accept/)per tutti i nodi figlio dello smart tag e delle chiamate[`VisitSmartTagEnd`](../../../aspose.words/documentvisitor/visitsmarttagend/) alla fine.

### Esempi

Mostra come creare smart tag.

```csharp
public void Create()
{
    Document doc = new Document();

    // Uno smart tag appare in un documento con Microsoft Word riconosce una parte del suo testo come una forma di dati,
    // come un nome, una data o un indirizzo e lo converte in un collegamento ipertestuale che visualizza una sottolineatura tratteggiata viola.
    SmartTag smartTag = new SmartTag(doc);

    // Gli smart tag sono nodi compositi che contengono il testo riconosciuto nella sua interezza.
    // Aggiungi contenuti a questo smart tag manualmente.
    smartTag.AppendChild(new Run(doc, "May 29, 2019"));

    // Microsoft Word potrebbe riconoscere il contenuto di cui sopra come una data.
    // Gli smart tag utilizzano la proprietà "Element" per riflettere il tipo di dati che contengono.
    smartTag.Element = "date";

    // Alcuni tipi di smart tag elaborano ulteriormente il loro contenuto in proprietà XML personalizzate.
    smartTag.Properties.Add(new CustomXmlProperty("Day", string.Empty, "29"));
    smartTag.Properties.Add(new CustomXmlProperty("Month", string.Empty, "5"));
    smartTag.Properties.Add(new CustomXmlProperty("Year", string.Empty, "2019"));

    // Imposta l'URI dello smart tag sul valore predefinito.
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a date. "));

    // Crea un altro smart tag per un ticker di borsa.
    smartTag = new SmartTag(doc);
    smartTag.Element = "stockticker";
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    smartTag.AppendChild(new Run(doc, "MSFT"));

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a stock ticker."));

    // Stampa tutti gli smart tag nel nostro documento utilizzando un visitatore del documento.
    doc.Accept(new SmartTagPrinter());

    // Le versioni precedenti di Microsoft Word supportano gli smart tag.
    doc.Save(ArtifactsDir + "SmartTag.Create.doc");

    // Usa il metodo "RemoveSmartTags" per rimuovere tutti gli smart tag da un documento.
    Assert.AreEqual(2, doc.GetChildNodes(NodeType.SmartTag, true).Count);

    doc.RemoveSmartTags();

    Assert.AreEqual(0, doc.GetChildNodes(NodeType.SmartTag, true).Count);
}

/// <summary>
/// Stampa gli smart tag visitati e il loro contenuto.
/// </summary>
private class SmartTagPrinter : DocumentVisitor
{
    /// <summary>
    /// Chiamato quando viene rilevato un nodo SmartTag nel documento.
    /// </summary>
    public override VisitorAction VisitSmartTagStart(SmartTag smartTag)
    {
        Console.WriteLine($"Smart tag type: {smartTag.Element}");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Chiamato al termine della visita di un nodo SmartTag.
    /// </summary>
    public override VisitorAction VisitSmartTagEnd(SmartTag smartTag)
    {
        Console.WriteLine($"\tContents: \"{smartTag.ToString(SaveFormat.Text)}\"");

        if (smartTag.Properties.Count == 0)
        {
            Console.WriteLine("\tContains no properties");
        }
        else
        {
            Console.Write("\tProperties: ");
            string[] properties = new string[smartTag.Properties.Count];
            int index = 0;

            foreach (CustomXmlProperty cxp in smartTag.Properties)
                properties[index++] = $"\"{cxp.Name}\" = \"{cxp.Value}\"";

            Console.WriteLine(string.Join(", ", properties));
        }

        return VisitorAction.Continue;
    }
}
```

### Guarda anche

* class [DocumentVisitor](../../../aspose.words/documentvisitor/)
* class [SmartTag](../)
* spazio dei nomi [Aspose.Words.Markup](../../smarttag/)
* assemblea [Aspose.Words](../../../)


