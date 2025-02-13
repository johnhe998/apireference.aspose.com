---
title: LayoutOptions.TextShaperFactory
second_title: Referencia de API de Aspose.Words para .NET
description: LayoutOptions propiedad. Obtiene o estableceITextShaperFactory implementación utilizada para funciones de representación de tipografía avanzada.
type: docs
weight: 90
url: /es/net/aspose.words.layout/layoutoptions/textshaperfactory/
---
## LayoutOptions.TextShaperFactory property

Obtiene o establece[`ITextShaperFactory`](../../../aspose.words.shaping/itextshaperfactory/) implementación utilizada para funciones de representación de tipografía avanzada.

```csharp
public ITextShaperFactory TextShaperFactory { get; set; }
```

### Ejemplos

Muestra cómo admitir funciones OpenType mediante el motor de forma de texto HarfBuzz.

```csharp
Document doc = new Document(MyDir + "OpenType text shaping.docx");

// Aspose.Words puede usar objetos modeladores de texto proporcionados externamente,
// que representan fuentes y calculan información de forma para el texto.
// Se necesita una fábrica de modelado de texto para los documentos que utilizan varias fuentes.
// Cuando se establece la configuración de fábrica del modelador de texto, el diseño utiliza funciones OpenType.
// Una propiedad Instance devuelve un objeto estático BasicTextShaperCache que envuelve HarfBuzzTextShaperFactory.
doc.LayoutOptions.TextShaperFactory = HarfBuzzTextShaperFactory.Instance;

// Actualmente, se está dando forma al texto cuando se exporta a formatos PDF o XPS.
doc.Save(ArtifactsDir + "Document.OpenType.pdf");
```

### Ver también

* interface [ITextShaperFactory](../../../aspose.words.shaping/itextshaperfactory/)
* class [LayoutOptions](../)
* espacio de nombres [Aspose.Words.Layout](../../layoutoptions/)
* asamblea [Aspose.Words](../../../)


