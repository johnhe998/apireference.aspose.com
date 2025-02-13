---
title: StructuredDocumentTag.IsTemporary
second_title: Referencia de API de Aspose.Words para .NET
description: StructuredDocumentTag propiedad. Especifica si este SDT se eliminará del documento WordProcessingML cuando se modifique su contenido .
type: docs
weight: 160
url: /es/net/aspose.words.markup/structureddocumenttag/istemporary/
---
## StructuredDocumentTag.IsTemporary property

Especifica si este **SDT** se eliminará del documento WordProcessingML cuando se modifique su contenido .

```csharp
public bool IsTemporary { get; set; }
```

### Ejemplos

Muestra cómo hacer controles de un solo uso.

```csharp
Document doc = new Document();

// Insertar una etiqueta de documento estructurado de texto sin formato,
// que actuará como un formulario de texto sin formato en el que el usuario puede ingresar texto.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Establezca la propiedad "IsTemporary" en "true" para que desaparezca la etiqueta del documento estructurado y
// asimilar su contenido en el documento después de que el usuario lo edite una vez en Microsoft Word.
// Establecer la propiedad "IsTemporary" en "falso" para permitir que el usuario edite los contenidos
// de la etiqueta del documento estructurado cualquier número de veces.
tag.IsTemporary = isTemporary;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Please enter text: ");
builder.InsertNode(tag);

// Inserte otra etiqueta de documento estructurado en forma de casilla de verificación y establezca su estado predeterminado en "marcado".
tag = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
tag.Checked = true;

// Establecer la propiedad "IsTemporary" en "true" para que la casilla de verificación se convierta en un símbolo
// una vez que el usuario hace clic en él en Microsoft Word.
// Establezca la propiedad "IsTemporary" en "false" para permitir que el usuario haga clic en la casilla de verificación cualquier número de veces.
tag.IsTemporary = isTemporary;

builder.Write("\nPlease click the check box: ");
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.IsTemporary.docx");
```

### Ver también

* class [StructuredDocumentTag](../)
* espacio de nombres [Aspose.Words.Markup](../../structureddocumenttag/)
* asamblea [Aspose.Words](../../../)


