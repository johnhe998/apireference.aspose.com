---
title: CompositeNode.SelectSingleNode
second_title: Aspose.Words per .NET API Reference
description: CompositeNode metodo. Seleziona il primo nodo che corrisponde allespressione XPath.
type: docs
weight: 210
url: /it/net/aspose.words/compositenode/selectsinglenode/
---
## CompositeNode.SelectSingleNode method

Seleziona il primo nodo che corrisponde all'espressione XPath.

```csharp
public Node SelectSingleNode(string xpath)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| xpath | String | L'espressione XPath. |

### Valore di ritorno

Il primo nodo che corrisponde alla query XPath o null se non viene trovato alcun nodo corrispondente.

### Osservazioni

Al momento sono supportate solo le espressioni con nomi di elementi. Le espressioni che utilizzano i nomi degli attributi non sono supportate.

### Esempi

Mostra come selezionare determinati nodi usando un'espressione XPath.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Questa espressione estrarrà tutti i nodi di paragrafo,
// che sono discendenti di qualsiasi nodo della tabella nel documento.
NodeList nodeList = doc.SelectNodes("//Tabella//Paragrafo");

// Scorri l'elenco con un enumeratore e stampa il contenuto di ogni paragrafo in ogni cella della tabella.
int index = 0;

using (IEnumerator<Node> e = nodeList.GetEnumerator())
    while (e.MoveNext())
        Console.WriteLine($"Table paragraph index {index++}, contents: \"{e.Current.GetText().Trim()}\"");

// Questa espressione selezionerà tutti i paragrafi che sono figli diretti di qualsiasi nodo Body nel documento.
nodeList = doc.SelectNodes("//Corpo/Paragrafo");

// Possiamo trattare l'elenco come un array.
Assert.AreEqual(4, nodeList.ToArray().Length);

// Usa SelectSingleNode per selezionare il primo risultato della stessa espressione di cui sopra.
Node node = doc.SelectSingleNode("//Corpo/Paragrafo");

Assert.AreEqual(typeof(Paragraph), node.GetType());
```

### Guarda anche

* class [Node](../../node/)
* class [CompositeNode](../)
* spazio dei nomi [Aspose.Words](../../compositenode/)
* assemblea [Aspose.Words](../../../)


