---
title: Class StyleCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.StyleCollection classe. Una raccolta di oggetti Style che rappresentano sia gli stili incorporati che quelli definiti dallutente in un documento.
type: docs
weight: 5840
url: /it/net/aspose.words/stylecollection/
---
## StyleCollection class

Una raccolta di oggetti Style che rappresentano sia gli stili incorporati che quelli definiti dall'utente in un documento.

```csharp
public class StyleCollection : IEnumerable<Style>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words/stylecollection/count/) { get; } | Ottiene il numero di stili nella raccolta. |
| [DefaultFont](../../aspose.words/stylecollection/defaultfont/) { get; } | Ottiene la formattazione del testo predefinita del documento. |
| [DefaultParagraphFormat](../../aspose.words/stylecollection/defaultparagraphformat/) { get; } | Ottiene la formattazione del paragrafo predefinita del documento. |
| [Document](../../aspose.words/stylecollection/document/) { get; } | Ottiene il documento proprietario. |
| [Item](../../aspose.words/stylecollection/item/) { get; } | Ottiene uno stile per nome o alias. (3 indexers) |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Add](../../aspose.words/stylecollection/add/)(StyleType, string) | Crea un nuovo stile definito dall'utente e lo aggiunge alla raccolta. |
| [AddCopy](../../aspose.words/stylecollection/addcopy/)(Style) | Copia uno stile in questa raccolta. |
| [ClearQuickStyleGallery](../../aspose.words/stylecollection/clearquickstylegallery/)() | Rimuove tutti gli stili dal pannello Galleria di stili rapidi. |
| [GetEnumerator](../../aspose.words/stylecollection/getenumerator/)() | Ottiene un oggetto enumeratore che enumera gli stili nell'ordine alfabetico dei loro nomi. |

### Esempi

Mostra come creare e utilizzare uno stile di paragrafo con la formattazione dell'elenco.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea uno stile di paragrafo personalizzato.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Crea un elenco e assicurati che i paragrafi che utilizzano questo stile utilizzeranno questo elenco.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Applica lo stile di paragrafo al paragrafo corrente del generatore di documenti, quindi aggiungi del testo.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Cambia lo stile del generatore di documenti in uno che non ha formattazione dell'elenco e scrivi un altro paragrafo.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Guarda anche

* class [Style](../style/)
* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


