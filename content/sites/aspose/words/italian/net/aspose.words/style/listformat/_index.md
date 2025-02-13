---
title: Style.ListFormat
second_title: Aspose.Words per .NET API Reference
description: Style proprietà. Fornisce laccesso alle proprietà di formattazione dellelenco di uno stile di paragrafo.
type: docs
weight: 100
url: /it/net/aspose.words/style/listformat/
---
## Style.ListFormat property

Fornisce l'accesso alle proprietà di formattazione dell'elenco di uno stile di paragrafo.

```csharp
public ListFormat ListFormat { get; }
```

### Osservazioni

Questa proprietà è valida solo per gli stili di paragrafo. Per altri tipi di stile questa proprietà restituisce null.

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

* class [ListFormat](../../../aspose.words.lists/listformat/)
* class [Style](../)
* spazio dei nomi [Aspose.Words](../../style/)
* assemblea [Aspose.Words](../../../)


