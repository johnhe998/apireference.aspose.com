---
title: SvgSaveOptions.ShowPageBorder
second_title: Referencia de API de Aspose.Words para .NET
description: SvgSaveOptions propiedad. Controla si se agrega un borde al contorno de la página. El valor predeterminado esverdadero .
type: docs
weight: 80
url: /es/net/aspose.words.saving/svgsaveoptions/showpageborder/
---
## SvgSaveOptions.ShowPageBorder property

Controla si se agrega un borde al contorno de la página. El valor predeterminado es`verdadero` .

```csharp
public bool ShowPageBorder { get; set; }
```

### Ejemplos

Muestra cómo imitar las propiedades de las imágenes al convertir un documento .docx a .svg.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Configure el objeto SvgSaveOptions para guardar sin bordes de página ni texto seleccionable.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### Ver también

* class [SvgSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../svgsaveoptions/)
* asamblea [Aspose.Words](../../../)


