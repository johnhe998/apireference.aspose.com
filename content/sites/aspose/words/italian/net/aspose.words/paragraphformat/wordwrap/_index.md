---
title: ParagraphFormat.WordWrap
second_title: Aspose.Words per .NET API Reference
description: ParagraphFormat proprietà. Se questa proprietà è falso il testo latino nel mezzo di una parola può essere avvolto per il paragrafo corrente. Altrimenti il testo latino è racchiuso da parole intere.
type: docs
weight: 400
url: /it/net/aspose.words/paragraphformat/wordwrap/
---
## ParagraphFormat.WordWrap property

Se questa proprietà è **falso** il testo latino nel mezzo di una parola può essere avvolto per il paragrafo corrente. Altrimenti il testo latino è racchiuso da parole intere.

```csharp
public bool WordWrap { get; set; }
```

### Esempi

Mostra come impostare proprietà speciali per la tipografia asiatica.

```csharp
Document doc = new Document(MyDir + "Document.docx");

ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.FarEastLineBreakControl = true;
format.WordWrap = false;
format.HangingPunctuation = true;

doc.Save(ArtifactsDir + "ParagraphFormat.AsianTypographyProperties.docx");
```

### Guarda anche

* class [ParagraphFormat](../)
* spazio dei nomi [Aspose.Words](../../paragraphformat/)
* assemblea [Aspose.Words](../../../)


