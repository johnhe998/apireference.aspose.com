---
title: StructuredDocumentTag.BuildingBlockCategory
second_title: Referencia de API de Aspose.Words para .NET
description: StructuredDocumentTag propiedad. Especifica la categoría de bloque de construcción para este SDT nodo. No puede ser nulo.
type: docs
weight: 30
url: /es/net/aspose.words.markup/structureddocumenttag/buildingblockcategory/
---
## StructuredDocumentTag.BuildingBlockCategory property

Especifica la categoría de bloque de construcción para este **SDT** nodo. No puede ser nulo.

```csharp
public string BuildingBlockCategory { get; set; }
```

### Observaciones

El acceso a esta propiedad solo funcionará paraBuildingBlockGallery y DocPartObj tipos de SDT. es de solo lectura para **SDT**del tipo de parte del documento.

Para todos los demás tipos de SDT, se producirá una excepción.

### Ejemplos

Muestra cómo insertar una etiqueta de documento estructurado como un bloque de creación y establecer su categoría y galería.

```csharp
Document doc = new Document();

StructuredDocumentTag buildingBlockSdt =
    new StructuredDocumentTag(doc, SdtType.BuildingBlockGallery, MarkupLevel.Block)
    {
        BuildingBlockCategory = "Built-in",
        BuildingBlockGallery = "Table of Contents"
    };

doc.FirstSection.Body.AppendChild(buildingBlockSdt);

doc.Save(ArtifactsDir + "StructuredDocumentTag.BuildingBlockCategories.docx");
```

### Ver también

* class [StructuredDocumentTag](../)
* espacio de nombres [Aspose.Words.Markup](../../structureddocumenttag/)
* asamblea [Aspose.Words](../../../)


