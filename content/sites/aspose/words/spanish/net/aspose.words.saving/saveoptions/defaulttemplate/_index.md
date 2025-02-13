---
title: SaveOptions.DefaultTemplate
second_title: Referencia de API de Aspose.Words para .NET
description: SaveOptions propiedad. Obtiene o establece la ruta a la plantilla predeterminada incluido el nombre de archivo. El valor predeterminado para esta propiedad es cuerda vacía Empty .
type: docs
weight: 40
url: /es/net/aspose.words.saving/saveoptions/defaulttemplate/
---
## SaveOptions.DefaultTemplate property

Obtiene o establece la ruta a la plantilla predeterminada (incluido el nombre de archivo). El valor predeterminado para esta propiedad es **cuerda vacía** (Empty ).

```csharp
public string DefaultTemplate { get; set; }
```

### Observaciones

Si se especifica, esta ruta se utiliza para cargar la plantilla cuando[`AutomaticallyUpdateStyles`](../../../aspose.words/document/automaticallyupdatestyles/) es cierto, pero[`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) esta vacio.

### Ejemplos

Muestra cómo configurar una plantilla predeterminada para documentos que no tienen plantillas adjuntas.

```csharp
Document doc = new Document();

// Habilite la actualización automática de estilo, pero no adjunte un documento de plantilla.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Dado que no hay un documento de plantilla, el documento no tenía dónde rastrear los cambios de estilo.
// Usar un objeto SaveOptions para configurar automáticamente una plantilla
// si un documento que estamos guardando no lo tiene.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Ver también

* class [SaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../saveoptions/)
* asamblea [Aspose.Words](../../../)


