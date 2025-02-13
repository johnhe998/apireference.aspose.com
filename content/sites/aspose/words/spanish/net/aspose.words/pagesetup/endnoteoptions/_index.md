---
title: PageSetup.EndnoteOptions
second_title: Referencia de API de Aspose.Words para .NET
description: PageSetup propiedad. Proporciona opciones que controlan la numeración y el posicionamiento de las notas finales en esta sección.
type: docs
weight: 120
url: /es/net/aspose.words/pagesetup/endnoteoptions/
---
## PageSetup.EndnoteOptions property

Proporciona opciones que controlan la numeración y el posicionamiento de las notas finales en esta sección.

```csharp
public EndnoteOptions EndnoteOptions { get; }
```

### Ejemplos

Muestra cómo configurar las opciones que afectan a las notas al pie/notas al final de una sección.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote reference text.");

// Configure todas las notas al pie en la primera sección para reiniciar la numeración desde 1
// en cada página nueva y se muestran directamente debajo del texto en cada página.
FootnoteOptions footnoteOptions = doc.Sections[0].PageSetup.FootnoteOptions;
footnoteOptions.Position = FootnotePosition.BeneathText;
footnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
footnoteOptions.StartNumber = 1;

builder.Write(" Hello again.");
builder.InsertFootnote(FootnoteType.Footnote, "Endnote reference text.");

// Configure todas las notas finales en la primera sección para mantener un conteo continuo a lo largo de la sección,
// a partir de 1. Además, configúrelos todos para que aparezcan recopilados al final del documento.
EndnoteOptions endnoteOptions = doc.Sections[0].PageSetup.EndnoteOptions;
endnoteOptions.Position = EndnotePosition.EndOfDocument;
endnoteOptions.RestartRule = FootnoteNumberingRule.Continuous;
endnoteOptions.StartNumber = 1;

doc.Save(ArtifactsDir + "PageSetup.FootnoteOptions.docx");
```

### Ver también

* class [EndnoteOptions](../../../aspose.words.notes/endnoteoptions/)
* class [PageSetup](../)
* espacio de nombres [Aspose.Words](../../pagesetup/)
* asamblea [Aspose.Words](../../../)


