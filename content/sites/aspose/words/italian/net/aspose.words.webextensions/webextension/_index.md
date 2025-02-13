---
title: Class WebExtension
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.WebExtensions.WebExtension classe. Rappresenta un oggetto estensione web.
type: docs
weight: 6430
url: /it/net/aspose.words.webextensions/webextension/
---
## WebExtension class

Rappresenta un oggetto estensione web.

```csharp
public class WebExtension
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [AlternateReferences](../../aspose.words.webextensions/webextension/alternatereferences/) { get; } | Specifica riferimenti alternativi a un'estensione Web. |
| [Bindings](../../aspose.words.webextensions/webextension/bindings/) { get; } | Specifica un elenco di associazioni di estensioni Web. |
| [Id](../../aspose.words.webextensions/webextension/id/) { get; set; } | Identifica in modo univoco l'istanza dell'estensione Web nel documento corrente. |
| [IsFrozen](../../aspose.words.webextensions/webextension/isfrozen/) { get; set; } | Specifica se l'utente può interagire con l'estensione Web o meno. |
| [Properties](../../aspose.words.webextensions/webextension/properties/) { get; } | Rappresenta un insieme di proprietà personalizzate dell'estensione web. |
| [Reference](../../aspose.words.webextensions/webextension/reference/) { get; } | Specifica il riferimento principale a un'estensione Web. |

### Esempi

Mostra come aggiungere un'estensione Web a un documento.

```csharp
Document doc = new Document();

// Crea il riquadro delle attività con il componente aggiuntivo "MyScript", che verrà utilizzato dal documento,
// quindi imposta la sua posizione predefinita.
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// Se ci sono più riquadri attività nella stessa posizione di ancoraggio, possiamo impostare questo indice per organizzarli.
myScriptTaskPane.Row = 1;

// Crea un componente aggiuntivo chiamato "MyScript Math Sample", che verrà visualizzato nel riquadro attività.
WebExtension webExtension = myScriptTaskPane.WebExtension;

// Imposta i parametri di riferimento dell'archivio applicazioni per il nostro componente aggiuntivo, come l'ID.
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// Consenti all'utente di interagire con il componente aggiuntivo.
webExtension.IsFrozen = false;

// Possiamo accedere all'estensione web in Microsoft Word tramite Developer -> Componenti aggiuntivi.
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// Rimuovi tutti i riquadri delle attività delle estensioni Web contemporaneamente in questo modo.
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* assemblea [Aspose.Words](../../)


