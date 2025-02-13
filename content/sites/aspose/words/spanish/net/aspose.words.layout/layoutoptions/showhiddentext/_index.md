---
title: LayoutOptions.ShowHiddenText
second_title: Referencia de API de Aspose.Words para .NET
description: LayoutOptions propiedad. Obtiene o establece una indicación de si se representa el texto oculto en el documento. El valor predeterminado es Falso.
type: docs
weight: 70
url: /es/net/aspose.words.layout/layoutoptions/showhiddentext/
---
## LayoutOptions.ShowHiddenText property

Obtiene o establece una indicación de si se representa el texto oculto en el documento. El valor predeterminado es Falso.

```csharp
public bool ShowHiddenText { get; set; }
```

### Observaciones

Esta propiedad afecta a todo el contenido oculto, no solo al texto.

### Ejemplos

Muestra cómo ocultar texto en un documento de salida renderizado.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Insertar texto oculto, luego especificar si deseamos omitirlo de un documento renderizado.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

### Ver también

* class [LayoutOptions](../)
* espacio de nombres [Aspose.Words.Layout](../../layoutoptions/)
* asamblea [Aspose.Words](../../../)


