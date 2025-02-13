---
title: Class CustomXmlProperty
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Markup.CustomXmlProperty classe. Rappresenta un singolo attributo XML personalizzato o una proprietà smart tag.
type: docs
weight: 3700
url: /it/net/aspose.words.markup/customxmlproperty/
---
## CustomXmlProperty class

Rappresenta un singolo attributo XML personalizzato o una proprietà smart tag.

```csharp
public class CustomXmlProperty
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [CustomXmlProperty](customxmlproperty/)(string, string, string) | Inizializza una nuova istanza di questa classe. |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Name](../../aspose.words.markup/customxmlproperty/name/) { get; } | Specifica il nome dell'attributo XML personalizzato o della proprietà dello smart tag. |
| [Uri](../../aspose.words.markup/customxmlproperty/uri/) { get; set; } | Ottiene o imposta l'URI dello spazio dei nomi dell'attributo XML personalizzato o della proprietà dello smart tag. |
| [Value](../../aspose.words.markup/customxmlproperty/value/) { get; set; } | Ottiene o imposta il valore dell'attributo XML personalizzato o della proprietà smart tag. |

### Osservazioni

Usato come oggetto di a[`CustomXmlPropertyCollection`](../customxmlpropertycollection/) collezione.

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

* spazio dei nomi [Aspose.Words.Markup](../../aspose.words.markup/)
* assemblea [Aspose.Words](../../)


