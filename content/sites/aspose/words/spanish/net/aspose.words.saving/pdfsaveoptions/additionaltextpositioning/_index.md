---
title: PdfSaveOptions.AdditionalTextPositioning
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Un indicador que especifica si escribir o no operadores de posicionamiento de texto adicionales.
type: docs
weight: 20
url: /es/net/aspose.words.saving/pdfsaveoptions/additionaltextpositioning/
---
## PdfSaveOptions.AdditionalTextPositioning property

Un indicador que especifica si escribir o no operadores de posicionamiento de texto adicionales.

```csharp
public bool AdditionalTextPositioning { get; set; }
```

### Observaciones

Si`verdadero` , los operadores de posicionamiento de texto adicionales se escriben en el PDF de salida. Esto puede ayudar a superar los problemas de con el posicionamiento inexacto del texto con algunas impresoras. La desventaja es el aumento del tamaño del documento PDF.

El valor predeterminado es`falso`.

### Ejemplos

Muestre cómo escribir operadores de posicionamiento de texto adicionales.

```csharp
Document doc = new Document(MyDir + "Text positioning operators.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    TextCompression = PdfTextCompression.None,

    // Establecer la propiedad "AdditionalTextPositioning" en "true" para intentar corregir errores
    // posicionamiento del elemento en el PDF de salida, si lo hubiera, a costa de aumentar el tamaño del archivo.
    // Establezca la propiedad "AdditionalTextPositioning" en "false" para representar el documento como de costumbre.
    AdditionalTextPositioning = applyAdditionalTextPositioning
};

doc.Save(ArtifactsDir + "PdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


