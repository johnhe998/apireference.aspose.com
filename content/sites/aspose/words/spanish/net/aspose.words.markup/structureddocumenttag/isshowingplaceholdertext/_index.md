---
title: StructuredDocumentTag.IsShowingPlaceholderText
second_title: Referencia de API de Aspose.Words para .NET
description: StructuredDocumentTag propiedad. Especifica si el contenido de este SDT se interpretará que contiene marcador de posición text a diferencia de los contenidos de texto regulares dentro de la SDT.
type: docs
weight: 150
url: /es/net/aspose.words.markup/structureddocumenttag/isshowingplaceholdertext/
---
## StructuredDocumentTag.IsShowingPlaceholderText property

Especifica si el contenido de este **SDT** se interpretará que contiene marcador de posición text (a diferencia de los contenidos de texto regulares dentro de la SDT).

si se establece en verdadero, este estado se reanudará (mostrando texto de marcador de posición) al abrir este documento.

```csharp
public bool IsShowingPlaceholderText { get; set; }
```

### Ejemplos

Muestra cómo usar el contenido de un bloque de creación como texto de marcador de posición personalizado para una etiqueta de documento estructurado.

```csharp
Document doc = new Document();

// Inserte una etiqueta de documento estructurado de texto sin formato del tipo "PlainText", que funcionará como un cuadro de texto.
// El contenido que mostrará por defecto es un "Haga clic aquí para ingresar texto". inmediato.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Podemos hacer que la etiqueta muestre el contenido de un bloque de construcción en lugar del texto predeterminado.
// Primero, agregue un bloque de construcción con contenido al documento del glosario.
GlossaryDocument glossaryDoc = doc.GlossaryDocument;

BuildingBlock substituteBlock = new BuildingBlock(glossaryDoc);
substituteBlock.Name = "Custom Placeholder";
substituteBlock.AppendChild(new Section(glossaryDoc));
substituteBlock.FirstSection.AppendChild(new Body(glossaryDoc));
substituteBlock.FirstSection.Body.AppendParagraph("Custom placeholder text.");

glossaryDoc.AppendChild(substituteBlock);

// Luego, use la propiedad "PlaceholderName" de la etiqueta del documento estructurado para hacer referencia a ese bloque de creación por su nombre.
tag.PlaceholderName = "Custom Placeholder";

// Si "PlaceholderName" hace referencia a un bloque existente en el documento del glosario del documento principal,
// podremos verificar el bloque de construcción a través de la propiedad "Marcador de posición".
Assert.AreEqual(substituteBlock, tag.Placeholder);

// Establecer la propiedad "IsShowingPlaceholderText" en "true" para tratar el
// contenido actual de la etiqueta del documento estructurado como texto de marcador de posición.
// Esto significa que hacer clic en el cuadro de texto en Microsoft Word resaltará inmediatamente todo el contenido de la etiqueta.
// Establecer la propiedad "IsShowingPlaceholderText" en "false" para obtener el
// etiqueta de documento estructurado para tratar su contenido como texto que un usuario ya ha ingresado.
// Al hacer clic en este texto en Microsoft Word, se colocará el cursor parpadeante en la ubicación en la que se hizo clic.
tag.IsShowingPlaceholderText = isShowingPlaceholderText;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlaceholderBuildingBlock.docx");
```

### Ver también

* class [StructuredDocumentTag](../)
* espacio de nombres [Aspose.Words.Markup](../../structureddocumenttag/)
* asamblea [Aspose.Words](../../../)


