---
title: Class ListLabel
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Lists.ListLabel classe. Definisce le proprietà specifiche di unetichetta di elenco.
type: docs
weight: 3290
url: /it/net/aspose.words.lists/listlabel/
---
## ListLabel class

Definisce le proprietà specifiche di un'etichetta di elenco.

```csharp
public class ListLabel
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Font](../../aspose.words.lists/listlabel/font/) { get; } | Ottiene il carattere dell'etichetta dell'elenco. |
| [LabelString](../../aspose.words.lists/listlabel/labelstring/) { get; } | Ottiene una rappresentazione di stringa dell'etichetta dell'elenco. |
| [LabelValue](../../aspose.words.lists/listlabel/labelvalue/) { get; } | Ottiene un valore numerico per questa etichetta. |

### Esempi

Mostra come estrarre le etichette dell'elenco di tutti i paragrafi che sono elementi dell'elenco.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
doc.UpdateListLabels();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

// Trova se abbiamo l'elenco dei paragrafi. Nel nostro documento, il nostro elenco utilizza semplici numeri arabi,
// che iniziano alle tre e finiscono alle sei.
foreach (Paragraph paragraph in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{
    Console.WriteLine($"List item paragraph #{paras.IndexOf(paragraph)}");

    // Questo è il testo che otteniamo quando otteniamo quando emettiamo questo nodo in formato testo.
    // Questo output di testo ometterà le etichette dell'elenco. Taglia i caratteri di formattazione del paragrafo. 
    string paragraphText = paragraph.ToString(SaveFormat.Text).Trim();
    Console.WriteLine($"\tExported Text: {paragraphText}");

    ListLabel label = paragraph.ListLabel;

    // Ottiene la posizione del paragrafo nel livello corrente dell'elenco. Se abbiamo una lista con più livelli,
    // questo ci dirà quale posizione si trova a quel livello.
    Console.WriteLine($"\tNumerical Id: {label.LabelValue}");

    // Combinali insieme per includere l'etichetta dell'elenco con il testo nell'output.
    Console.WriteLine($"\tList label combined with text: {label.LabelString} {paragraphText}");
}
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Lists](../../aspose.words.lists/)
* assemblea [Aspose.Words](../../)


