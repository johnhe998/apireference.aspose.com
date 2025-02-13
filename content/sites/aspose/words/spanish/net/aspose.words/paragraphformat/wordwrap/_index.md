---
title: ParagraphFormat.WordWrap
second_title: Referencia de API de Aspose.Words para .NET
description: ParagraphFormat propiedad. Si esta propiedad es falso el texto en latín en medio de una palabra se puede ajustar para el párrafo actual. De lo contrario el texto en latín se envuelve con palabras completas.
type: docs
weight: 400
url: /es/net/aspose.words/paragraphformat/wordwrap/
---
## ParagraphFormat.WordWrap property

Si esta propiedad es **falso** el texto en latín en medio de una palabra se puede ajustar para el párrafo actual. De lo contrario, el texto en latín se envuelve con palabras completas.

```csharp
public bool WordWrap { get; set; }
```

### Ejemplos

Muestra cómo establecer propiedades especiales para la tipografía asiática.

```csharp
Document doc = new Document(MyDir + "Document.docx");

ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.FarEastLineBreakControl = true;
format.WordWrap = false;
format.HangingPunctuation = true;

doc.Save(ArtifactsDir + "ParagraphFormat.AsianTypographyProperties.docx");
```

### Ver también

* class [ParagraphFormat](../)
* espacio de nombres [Aspose.Words](../../paragraphformat/)
* asamblea [Aspose.Words](../../../)


