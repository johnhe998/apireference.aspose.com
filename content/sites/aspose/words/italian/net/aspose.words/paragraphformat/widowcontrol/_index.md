---
title: ParagraphFormat.WidowControl
second_title: Aspose.Words per .NET API Reference
description: ParagraphFormat proprietà. Vero se la prima e lultima riga del paragrafo devono rimanere sulla stessa pagina del resto del paragrafo.
type: docs
weight: 390
url: /it/net/aspose.words/paragraphformat/widowcontrol/
---
## ParagraphFormat.WidowControl property

Vero se la prima e l'ultima riga del paragrafo devono rimanere sulla stessa pagina del resto del paragrafo.

```csharp
public bool WidowControl { get; set; }
```

### Esempi

Mostra come abilitare il controllo vedova/orfano per un paragrafo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Quando scriviamo il testo che non si adatta a una pagina, una riga potrebbe riversarsi sulla pagina successiva.
// La singola riga che finisce nella pagina successiva è chiamata "Orphan",
// e la riga precedente in cui l'orfano si è interrotto è chiamata "Widow".
// Possiamo riparare orfani e vedove riorganizzando il testo in base alla dimensione del carattere, alla spaziatura o ai margini della pagina.
// Se desideriamo preservare le dimensioni del nostro documento, possiamo impostare questo flag su "true"
 // per spingere le vedove sulla stessa pagina dei rispettivi orfani.
// Lascia questo flag come "falso" lascerà coppie vedove/orfane nel testo.
// Ogni paragrafo ha questa impostazione accessibile in Microsoft Word tramite Home -> Paragrafo -> Impostazioni paragrafo
// (pulsante nell'angolo in basso a destra della scheda "Paragrafo") -> "Controllo vedova/orfano".
builder.ParagraphFormat.WidowControl = widowControl; 

// Inserisce del testo che produca un orfano e una vedova.
builder.Font.Size = 68;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "ParagraphFormat.WidowControl.docx");
```

### Guarda anche

* class [ParagraphFormat](../)
* spazio dei nomi [Aspose.Words](../../paragraphformat/)
* assemblea [Aspose.Words](../../../)


