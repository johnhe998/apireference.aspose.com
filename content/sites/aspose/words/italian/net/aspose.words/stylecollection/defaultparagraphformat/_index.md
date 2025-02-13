---
title: StyleCollection.DefaultParagraphFormat
second_title: Aspose.Words per .NET API Reference
description: StyleCollection proprietà. Ottiene la formattazione del paragrafo predefinita del documento.
type: docs
weight: 30
url: /it/net/aspose.words/stylecollection/defaultparagraphformat/
---
## StyleCollection.DefaultParagraphFormat property

Ottiene la formattazione del paragrafo predefinita del documento.

```csharp
public ParagraphFormat DefaultParagraphFormat { get; }
```

### Osservazioni

Si noti che le impostazioni predefinite a livello di documento sono state introdotte in Microsoft Word 2007 e sono completamente supportate nei formati OOXML (Docx) solo. I formati di documento precedenti non supportano la formattazione di paragrafo predefinita del documento.

### Esempi

Mostra come aggiungere uno stile alla raccolta di stili di un documento.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Imposta i parametri predefiniti per i nuovi stili che potremmo aggiungere in seguito a questa raccolta.
styles.DefaultFont.Name = "Courier New";

// Se aggiungiamo uno stile di "StyleType.Paragraph", la raccolta applicherà i valori di
// la sua proprietà "DefaultParagraphFormat" alla proprietà "ParagraphFormat" dello stile.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Aggiungi uno stile, quindi verifica che abbia le impostazioni predefinite.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### Guarda anche

* class [ParagraphFormat](../../paragraphformat/)
* class [StyleCollection](../)
* spazio dei nomi [Aspose.Words](../../stylecollection/)
* assemblea [Aspose.Words](../../../)


