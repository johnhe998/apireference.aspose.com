---
title: Enum ImportFormatMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.ImportFormatMode enum. Specifica come viene unita la formattazione durante limportazione di contenuto da un altro documento.
type: docs
weight: 3030
url: /it/net/aspose.words/importformatmode/
---
## ImportFormatMode enumeration

Specifica come viene unita la formattazione durante l'importazione di contenuto da un altro documento.

```csharp
public enum ImportFormatMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| UseDestinationStyles | `0` | Usa gli stili del documento di destinazione e copia i nuovi stili. Questa è l'opzione predefinita. |
| KeepSourceFormatting | `1` | Copia tutti gli stili richiesti nel documento di destinazione, genera nomi di stile univoci se necessario. |
| KeepDifferentStyles | `2` | Copia solo stili diversi da quelli nel documento di origine. |

### Osservazioni

Quando copi i nodi da un documento a un altro, questa opzione specifica come formatting viene risolta quando entrambi i documenti hanno uno stile con lo stesso nome, ma formattazione diversa.

La formattazione viene risolta come segue:

1. Gli stili incorporati vengono abbinati utilizzando l'identificatore di stile indipendente dalla locale. Gli stili definiti dall'utente vengono abbinati utilizzando il nome di stile con distinzione tra maiuscole e minuscole.
2. Se non viene trovato uno stile corrispondente nel documento di destinazione, lo stile (e tutti gli stili a cui fa riferimento) vengono copiati nel documento di destinazione e i nodi importati vengono aggiornati per fare riferimento al nuovo stile.
3. Se esiste già uno stile corrispondente nel documento di destinazione, ciò che accade dipende da`importFormatMode` parametro passato a [`Document.ImportNode`](../documentbase/importnode/) come descritto di seguito.

Quando si utilizza il **Usa gli stili di destinazione**opzione, se esiste già uno stile corrispondente nel documento di destinazione, lo stile non viene copiato ei nodi importati vengono aggiornati per fare riferimento allo stile esistente.

Lo svantaggio di usare **Usa gli stili di destinazione** è che il testo importato potrebbe avere un aspetto diverso nel documento di destinazione rispetto al documento di origine. Ad esempio, lo stile "Intestazione 1" nel documento di origine utilizza il carattere Arial 16pt e lo stile "Intestazione 1" nel documento di destinazione utilizza Times New Font Roman 14pt. Quando si importa il testo dello stile "Titolo 1" senza altra formattazione diretta, apparirà come font Times New Roman 14pt nel documento di destinazione.

**KeepSourceFormatting**l'opzione consente di assicurarsi che il contenuto importato abbia lo stesso aspetto nel documento di destinazione come appare nel documento di origine. Se esiste già uno stile corrispondente nel documento di destinazione, la formattazione dello stile di origine viene espansa negli attributi del nodo diretto e lo stile è modificato in Normale. Se lo stile non esiste nel documento di destinazione, lo stile di origine viene importato nel documento di destinazione e applicato al nodo importato. Nota che non è sempre possibile preservare lo stile di origine anche se non esiste nel documento di destinazione. In questo caso la formattazione di tale stile verrà espansa in attributi diretti del nodo a favore della conservazione della formattazione originale del nodo.

Lo svantaggio di usare **KeepSourceFormatting**è che se esegui diverse importazioni, potresti ritrovarti con molti stili nel documento di destinazione e ciò potrebbe rendere difficile l'utilizzo di una formattazione di stile coerente in Microsoft Word per questo documento.

Usando **KeepDifferentStyles** l'opzione consente di riutilizzare gli stili di destinazione se la formattazione fornita è identica agli stili nel documento di origine. Se lo stile nel documento di destinazione è diverso dall'origine, viene importato.

### Esempi

Mostra come inserire un documento in un altro documento.

```csharp
Document doc = new Document(MyDir + "Document.docx");

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);

Document docToInsert = new Document(MyDir + "Formatted elements.docx");

builder.InsertDocument(docToInsert, ImportFormatMode.KeepSourceFormatting);
builder.Document.Save(ArtifactsDir + "DocumentBuilder.InsertDocument.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


