---
title: CompositeNode.GetText
second_title: Aspose.Words per .NET API Reference
description: CompositeNode metodo. Ottiene il testo di questo nodo e di tutti i suoi figli.
type: docs
weight: 120
url: /it/net/aspose.words/compositenode/gettext/
---
## CompositeNode.GetText method

Ottiene il testo di questo nodo e di tutti i suoi figli.

```csharp
public override string GetText()
```

### Osservazioni

La stringa restituita include tutti i caratteri di controllo e speciali come descritto in[`ControlChar`](../../controlchar/).

### Esempi

Mostra la differenza tra la chiamata dei metodi GetText e ToString su un nodo.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("MERGEFIELD Field");

// GetText recupererà il testo visibile, codici di campo e caratteri speciali.
Assert.AreEqual("\u0013MERGEFIELD Field\u0014«Field»\u0015\u000c", doc.GetText());

// ToString ci darà l'aspetto del documento se salvato in un formato di salvataggio passato.
Assert.AreEqual("«Field»\r\n", doc.ToString(SaveFormat.Text));
```

Mostra come generare in output tutti i paragrafi di un documento che sono voci di elenco.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Numbered list item 1");
builder.Writeln("Numbered list item 2");
builder.Writeln("Numbered list item 3");
builder.ListFormat.RemoveNumbers();

builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Bulleted list item 1");
builder.Writeln("Bulleted list item 2");
builder.Writeln("Bulleted list item 3");
builder.ListFormat.RemoveNumbers();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{ 
    Console.WriteLine($"This paragraph belongs to list ID# {para.ListFormat.List.ListId}, number style \"{para.ListFormat.ListLevel.NumberStyle}\"");
    Console.WriteLine($"\t\"{para.GetText().Trim()}\"");
}
```

### Guarda anche

* class [CompositeNode](../)
* spazio dei nomi [Aspose.Words](../../compositenode/)
* assemblea [Aspose.Words](../../../)


