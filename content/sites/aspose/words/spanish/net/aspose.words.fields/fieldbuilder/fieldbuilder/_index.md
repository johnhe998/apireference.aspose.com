---
title: FieldBuilder.FieldBuilder
second_title: Referencia de API de Aspose.Words para .NET
description: FieldBuilder constructor. Inicializa una instancia delFieldBuilder clase.
type: docs
weight: 10
url: /es/net/aspose.words.fields/fieldbuilder/fieldbuilder/
---
## FieldBuilder constructor

Inicializa una instancia del[`FieldBuilder`](../) clase.

```csharp
public FieldBuilder(FieldType fieldType)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| fieldType | FieldType | El tipo de campo a construir. |

### Ejemplos

Muestra cómo crear e insertar un campo usando un generador de campos.

```csharp
Document doc = new Document();

// Una forma conveniente de agregar contenido de texto a un documento es con un generador de documentos.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write(" Hello world! This text is one Run, which is an inline node.");

// Los campos tienen su constructor, que podemos usar para construir un código de campo pieza por pieza.
// En este caso, construiremos un campo BARCODE que representa un código postal de EE. UU.,
// y luego insértelo delante de Run.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldBarcode);
fieldBuilder.AddArgument("90210");
fieldBuilder.AddSwitch("\\f", "A");
fieldBuilder.AddSwitch("\\u");

fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph.Runs[0]);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.CreateWithFieldBuilder.docx");
```

### Ver también

* enum [FieldType](../../fieldtype/)
* class [FieldBuilder](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldbuilder/)
* asamblea [Aspose.Words](../../../)


