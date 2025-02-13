---
title: Class CleanupOptions
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.CleanupOptions classe. Consente di specificare le opzioni per la pulizia dei documenti.
type: docs
weight: 200
url: /it/net/aspose.words/cleanupoptions/
---
## CleanupOptions class

Consente di specificare le opzioni per la pulizia dei documenti.

```csharp
public class CleanupOptions
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [CleanupOptions](cleanupoptions/)() | Default_Costruttore |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [DuplicateStyle](../../aspose.words/cleanupoptions/duplicatestyle/) { get; set; } | Ottiene/imposta un flag che indica se gli stili duplicati devono essere rimossi dal documento. Il valore predefinito è **falso** . |
| [UnusedBuiltinStyles](../../aspose.words/cleanupoptions/unusedbuiltinstyles/) { get; set; } | Specifica quello inutilizzato[`BuiltIn`](../style/builtin/) gli stili devono essere rimossi dal documento. |
| [UnusedLists](../../aspose.words/cleanupoptions/unusedlists/) { get; set; } | Specifica se l'elenco e le definizioni degli elenchi inutilizzati devono essere rimossi dal documento. Il valore predefinito è **VERO** . |
| [UnusedStyles](../../aspose.words/cleanupoptions/unusedstyles/) { get; set; } | Specifica se gli stili inutilizzati devono essere rimossi dal documento. Il valore predefinito è **VERO** . |

### Esempi

Mostra come rimuovere tutti gli stili personalizzati non utilizzati da un documento.

```csharp
Document doc = new Document();

doc.Styles.Add(StyleType.List, "MyListStyle1");
doc.Styles.Add(StyleType.List, "MyListStyle2");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle1");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle2");

// Combinato con gli stili incorporati, il documento ora ha otto stili.
// Uno stile personalizzato è contrassegnato come "usato" mentre è presente del testo all'interno del documento
// formattato in quello stile. Ciò significa che i 4 stili che abbiamo aggiunto non sono attualmente utilizzati.
Assert.AreEqual(8, doc.Styles.Count);

// Applica uno stile di carattere personalizzato, quindi uno stile di elenco personalizzato. In questo modo verranno contrassegnati come "usati".
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Style = doc.Styles["MyParagraphStyle1"];
builder.Writeln("Hello world!");

Aspose.Words.Lists.List list = doc.Lists.Add(doc.Styles["MyListStyle1"]);
builder.ListFormat.List = list;
builder.Writeln("Item 1");
builder.Writeln("Item 2");

// Ora c'è uno stile di carattere inutilizzato e uno stile di elenco inutilizzato.
// Il metodo Cleanup(), se configurato con un oggetto CleanupOptions, può indirizzare gli stili inutilizzati e rimuoverli.
CleanupOptions cleanupOptions = new CleanupOptions
{
    UnusedLists = true, UnusedStyles = true, UnusedBuiltinStyles = true
};

doc.Cleanup(cleanupOptions);

Assert.AreEqual(4, doc.Styles.Count);

// Rimuove ogni nodo a cui viene applicato uno stile personalizzato e lo contrassegna nuovamente come "non utilizzato". 
// Esegui nuovamente il metodo Cleanup per rimuoverli.
doc.FirstSection.Body.RemoveAllChildren();
doc.Cleanup(cleanupOptions);

Assert.AreEqual(2, doc.Styles.Count);
```

### Guarda anche

* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


