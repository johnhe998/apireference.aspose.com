---
title: Range.UpdateFields
second_title: Referencia de API de Aspose.Words para .NET
description: Range método. Actualiza los valores de los campos del documento en este rango.
type: docs
weight: 110
url: /es/net/aspose.words/range/updatefields/
---
## Range.UpdateFields method

Actualiza los valores de los campos del documento en este rango.

```csharp
public void UpdateFields()
```

### Observaciones

Cuando abre, modifica y luego guarda un documento, Aspose.Words no actualiza los campos automáticamente, los mantiene intactos. Por lo tanto, normalmente querrá llamar a este método antes de guardar si ha modificado el documento mediante programación y desea asegurarse los valores de campo correctos (calculados) aparecen en el documento guardado.

No es necesario actualizar los campos después de ejecutar una combinación de correspondencia porque la combinación de correspondencia es una especie de actualización de campo y actualiza automáticamente todos los campos del documento.

Este método no actualiza todos los tipos de campo. Para obtener una lista detallada de los tipos de campos admitidos, consulte la Guía del programador.

Este método no actualiza los campos que están relacionados con los algoritmos de diseño de página (por ejemplo, PÁGINA, PÁGINAS, PAGEREF). Los campos relacionados con el diseño de página se actualizan cuando procesa un documento o llama[`UpdatePageLayout`](../../document/updatepagelayout/).

Para actualizar campos en todo el documento use[`UpdateFields`](../../document/updatefields/).

### Ejemplos

Muestra cómo actualizar todos los campos en un rango.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" DOCPROPERTY Category");
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.InsertField(" DOCPROPERTY Category");

// Los campos DOCPROPERTY anteriores mostrarán el valor de esta propiedad de documento incorporada.
doc.BuiltInDocumentProperties.Category = "MyCategory";

// Si actualizamos el valor de una propiedad del documento, necesitaremos actualizar todos los campos DOCPROPERTY para mostrarlo.
Assert.AreEqual(string.Empty, doc.Range.Fields[0].Result);
Assert.AreEqual(string.Empty, doc.Range.Fields[1].Result);

// Actualizar todos los campos que están en el rango de la primera sección.
doc.FirstSection.Range.UpdateFields();

Assert.AreEqual("MyCategory", doc.Range.Fields[0].Result);
Assert.AreEqual(string.Empty, doc.Range.Fields[1].Result);
```

### Ver también

* class [Range](../)
* espacio de nombres [Aspose.Words](../../range/)
* asamblea [Aspose.Words](../../../)


