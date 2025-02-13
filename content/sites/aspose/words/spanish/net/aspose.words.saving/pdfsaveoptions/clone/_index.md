---
title: PdfSaveOptions.Clone
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions método. Crea un clon profundo de este objeto.
type: docs
weight: 310
url: /es/net/aspose.words.saving/pdfsaveoptions/clone/
---
## PdfSaveOptions.Clone method

Crea un clon profundo de este objeto.

```csharp
public PdfSaveOptions Clone()
```

### Ejemplos

Muestra cómo actualizar todos los campos de un documento inmediatamente antes de guardarlo en PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar texto con campos PAGE y NUMPAGES. Estos campos no muestran el valor correcto en tiempo real.
// Tendremos que actualizarlos manualmente usando métodos de actualización como "Field.Update()" y "Document.UpdateFields()"
// cada vez que los necesitamos para mostrar valores precisos.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Hello World!");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establezca la propiedad "UpdateFields" en "falso" para no actualizar todos los campos en un documento justo antes de una operación de guardado.
// Esta es la opción preferible si sabemos que todos nuestros campos estarán actualizados antes de guardar.
// Establecer la propiedad "UpdateFields" en "true" para recorrer todo el documento
// campos y actualícelos antes de guardarlo como PDF. Esto asegurará que todos los campos se muestren
// los valores más precisos en el PDF.
options.UpdateFields = updateFields;

// Podemos clonar objetos PdfSaveOptions.
Assert.AreNotSame(options, options.Clone());

doc.Save(ArtifactsDir + "PdfSaveOptions.UpdateFields.pdf", options);
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


