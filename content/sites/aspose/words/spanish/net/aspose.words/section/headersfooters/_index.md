---
title: Section.HeadersFooters
second_title: Referencia de API de Aspose.Words para .NET
description: Section propiedad. Proporciona acceso a los nodos de encabezados y pies de página de la sección.
type: docs
weight: 30
url: /es/net/aspose.words/section/headersfooters/
---
## Section.HeadersFooters property

Proporciona acceso a los nodos de encabezados y pies de página de la sección.

```csharp
public HeaderFooterCollection HeadersFooters { get; }
```

### Ejemplos

Muestra cómo reemplazar texto en el pie de página de un documento.

```csharp
Document doc = new Document(MyDir + "Footer.docx");

HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

FindReplaceOptions options = new FindReplaceOptions
{
    MatchCase = false,
    FindWholeWordsOnly = false
};

int currentYear = DateTime.Now.Year;
footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", $"Copyright (C) {currentYear} by Aspose Pty Ltd.", options);

doc.Save(ArtifactsDir + "HeaderFooter.ReplaceText.docx");
```

Muestra cómo eliminar todos los pies de página de un documento.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// Iterar a través de cada sección y eliminar pies de página de todo tipo.
foreach (Section section in doc.OfType<Section>())
{
    // Hay tres tipos de tipos de encabezado y pie de página.
    // 1 - El encabezado/pie de página "Primero", que solo aparece en la primera página de una sección.
    HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
    footer?.Remove();

    // 2 - El encabezado/pie de página "Principal", que aparece en las páginas impares.
    footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
    footer?.Remove();

      // 3 - El encabezado/pie de página "Even", que aparece en las páginas pares.
    footer = section.HeadersFooters[HeaderFooterType.FooterEven];
    footer?.Remove();

    Assert.AreEqual(0, section.HeadersFooters.Count(hf => !((HeaderFooter)hf).IsHeader));
}

doc.Save(ArtifactsDir + "HeaderFooter.RemoveFooters.docx");
```

### Ver también

* class [HeaderFooterCollection](../../headerfootercollection/)
* class [Section](../)
* espacio de nombres [Aspose.Words](../../section/)
* asamblea [Aspose.Words](../../../)


