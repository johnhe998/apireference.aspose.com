---
title: Class SubDocument
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.SubDocument classe. Rappresenta a Sottodocumento  che è un riferimento a un documento archiviato esternamente.
type: docs
weight: 5870
url: /it/net/aspose.words/subdocument/
---
## SubDocument class

Rappresenta a **Sottodocumento** - che è un riferimento a un documento archiviato esternamente.

```csharp
public class SubDocument : Node
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [CustomNodeId](../../aspose.words/node/customnodeid/) { get; set; } | Specifica l'identificatore del nodo personalizzato. |
| virtual [Document](../../aspose.words/node/document/) { get; } | Ottiene il documento a cui appartiene questo nodo. |
| virtual [IsComposite](../../aspose.words/node/iscomposite/) { get; } | Restituisce vero se questo nodo può contenere altri nodi. |
| [NextSibling](../../aspose.words/node/nextsibling/) { get; } | Ottiene il nodo immediatamente successivo a questo nodo. |
| override [NodeType](../../aspose.words/subdocument/nodetype/) { get; } | Restituisce **NodeType.SubDocument** |
| [ParentNode](../../aspose.words/node/parentnode/) { get; } | Ottiene il genitore immediato di questo nodo. |
| [PreviousSibling](../../aspose.words/node/previoussibling/) { get; } | Ottiene il nodo immediatamente precedente a questo nodo. |
| [Range](../../aspose.words/node/range/) { get; } | Restituisce a **Gamma** oggetto che rappresenta la parte di un documento contenuta in questo nodo. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| override [Accept](../../aspose.words/subdocument/accept/)(DocumentVisitor) | Accetta un visitatore. |
| [Clone](../../aspose.words/node/clone/)(bool) | Crea un duplicato del nodo. |
| [GetAncestor](../../aspose.words/node/getancestor/)(NodeType) | Ottiene il primo predecessore dell'oggetto specificato[`NodeType`](../nodetype/) . |
| [GetAncestor](../../aspose.words/node/getancestor/)(Type) | Ottiene il primo predecessore del tipo di oggetto specificato. |
| virtual [GetText](../../aspose.words/node/gettext/)() | Ottiene il testo di questo nodo e di tutti i suoi figli. |
| [NextPreOrder](../../aspose.words/node/nextpreorder/)(Node) | Ottiene il nodo successivo in base all'algoritmo di attraversamento dell'albero di preordine. |
| [PreviousPreOrder](../../aspose.words/node/previouspreorder/)(Node) | Ottiene il nodo precedente in base all'algoritmo di attraversamento dell'albero di preordine. |
| [Remove](../../aspose.words/node/remove/)() | Si rimuove dal genitore. |
| [ToString](../../aspose.words/node/tostring/)(SaveFormat) | Esporta il contenuto del nodo in una stringa nel formato specificato. |
| [ToString](../../aspose.words/node/tostring/)(SaveOptions) | Esporta il contenuto del nodo in una stringa utilizzando le opzioni di salvataggio specificate. |

### Osservazioni

In questa versione di Aspose.Words,`SubDocument` i nodi non forniscono metodi pubblici e proprietà per creare o modificare un documento secondario. In questa versione non è possibile creare un'istanza di nodi SubDocument o modificare esistenti se non eliminandoli.

`SubDocument` può essere solo un figlio di[`Paragraph`](../paragraph/).

### Esempi

Mostra come accedere al documento secondario di un documento master.

```csharp
Document doc = new Document(MyDir + "Master document.docx");

NodeCollection subDocuments = doc.GetChildNodes(NodeType.SubDocument, true);
// Questo nodo funge da riferimento a un documento esterno e non è possibile accedere al suo contenuto.
SubDocument subDocument = (SubDocument)subDocuments[0];

Assert.False(subDocument.IsComposite);
```

### Guarda anche

* class [Node](../node/)
* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


