---
title: FieldIndex.CrossReferenceSeparator
second_title: Referencia de API de Aspose.Words para .NET
description: FieldIndex propiedad. Obtiene o establece la secuencia de caracteres que se utiliza para separar las referencias cruzadas y otras entradas.
type: docs
weight: 30
url: /es/net/aspose.words.fields/fieldindex/crossreferenceseparator/
---
## FieldIndex.CrossReferenceSeparator property

Obtiene o establece la secuencia de caracteres que se utiliza para separar las referencias cruzadas y otras entradas.

```csharp
public string CrossReferenceSeparator { get; set; }
```

### Ejemplos

Muestra cómo definir referencias cruzadas en un campo ÍNDICE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Cree un campo ÍNDICE que mostrará una entrada para cada campo XE encontrado en el documento.
// Cada entrada mostrará el valor de la propiedad Texto del campo XE en el lado izquierdo,
// y el número de la página que contiene el campo XE a la derecha.
// La entrada ÍNDICE recopilará todos los campos XE con valores coincidentes en la propiedad "Texto"
// en una entrada en lugar de hacer una entrada para cada campo XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Podemos configurar un campo XE para obtener su entrada ÍNDICE para mostrar una cadena en lugar de un número de página.
// Primero, para las entradas que sustituyen un número de página con una cadena,
// especifique un separador personalizado entre el valor de la propiedad Texto del campo XE y la cadena.
index.CrossReferenceSeparator = ", see: ";

Assert.AreEqual(" INDEX  \\k \", see: \"", index.GetFieldCode());

// Inserte un campo XE, que crea una entrada de ÍNDICE regular que muestra el número de página de este campo,
// y no invoca el valor de CrossReferenceSeparator.
// La entrada para este campo XE mostrará "Apple, 2".
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apple";

Assert.AreEqual(" XE  Apple", indexEntry.GetFieldCode());

// Inserte otro campo XE en la página 3 y establezca un valor para la propiedad PageNumberReplacement.
// Este valor aparecerá en lugar del número de la página en la que se encuentra este campo,
// y el valor CrossReferenceSeparator del campo ÍNDICE aparecerá delante de él.
// La entrada para este campo XE mostrará "Plátano, véase: Fruta tropical".
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Banana";
indexEntry.PageNumberReplacement = "Tropical fruit";

Assert.AreEqual(" XE  Banana \\t \"Tropical fruit\"", indexEntry.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.CrossReferenceSeparator.docx");
```

### Ver también

* class [FieldIndex](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldindex/)
* asamblea [Aspose.Words](../../../)


