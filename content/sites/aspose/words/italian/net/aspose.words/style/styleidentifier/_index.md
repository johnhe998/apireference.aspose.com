---
title: Style.StyleIdentifier
second_title: Aspose.Words per .NET API Reference
description: Style proprietà. Ottiene lidentificatore di stile indipendente dalla locale per uno stile integrato.
type: docs
weight: 140
url: /it/net/aspose.words/style/styleidentifier/
---
## Style.StyleIdentifier property

Ottiene l'identificatore di stile indipendente dalla locale per uno stile integrato.

```csharp
public StyleIdentifier StyleIdentifier { get; }
```

### Osservazioni

Per gli stili definiti dall'utente (personalizzati), questa proprietà restituisceUser.

### Esempi

Mostra come modificare la posizione della tabulazione destra nei paragrafi relativi al sommario.

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// Scorri tutti i paragrafi con stili basati sui risultati del sommario; questo è qualsiasi stile tra TOC e TOC9.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Ottieni la prima scheda utilizzata in questo paragrafo, questa dovrebbe essere la scheda utilizzata per allineare i numeri di pagina.
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // Sostituisci la prima tabulazione predefinita, ferma con una tabulazione personalizzata.
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### Guarda anche

* enum [StyleIdentifier](../../styleidentifier/)
* class [Style](../)
* spazio dei nomi [Aspose.Words](../../style/)
* assemblea [Aspose.Words](../../../)


