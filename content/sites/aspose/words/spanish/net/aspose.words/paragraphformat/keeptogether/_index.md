---
title: ParagraphFormat.KeepTogether
second_title: Referencia de API de Aspose.Words para .NET
description: ParagraphFormat propiedad. Verdadero si todas las líneas del párrafo deben permanecer en la misma página.
type: docs
weight: 150
url: /es/net/aspose.words/paragraphformat/keeptogether/
---
## ParagraphFormat.KeepTogether property

Verdadero si todas las líneas del párrafo deben permanecer en la misma página.

```csharp
public bool KeepTogether { get; set; }
```

### Ejemplos

Muestra cómo insertar un párrafo en el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;
paragraphFormat.KeepTogether = true;

// El método "Writeln" finaliza el párrafo después de agregar texto
// y luego comienza una nueva línea, agregando un nuevo párrafo.
builder.Writeln("Hello world!");

Assert.True(builder.CurrentParagraph.IsEndOfDocument);
```

### Ver también

* class [ParagraphFormat](../)
* espacio de nombres [Aspose.Words](../../paragraphformat/)
* asamblea [Aspose.Words](../../../)


