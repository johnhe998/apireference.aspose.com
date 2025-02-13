---
title: FieldPrint.PostScriptGroup
second_title: Referencia de API de Aspose.Words para .NET
description: FieldPrint propiedad. Obtiene o establece el rectángulo de dibujo sobre el que operan las instrucciones PostScript.
type: docs
weight: 20
url: /es/net/aspose.words.fields/fieldprint/postscriptgroup/
---
## FieldPrint.PostScriptGroup property

Obtiene o establece el rectángulo de dibujo sobre el que operan las instrucciones PostScript.

```csharp
public string PostScriptGroup { get; set; }
```

### Ejemplos

Muestra para insertar un campo IMPRIMIR.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// El campo PRINT puede enviar instrucciones a la impresora.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// Establecer el área para que la impresora realice las instrucciones.
// En este caso, será el párrafo que contiene nuestro campo PRINT.
field.PostScriptGroup = "para";

// Cuando usamos una impresora que soporta PostScript para imprimir nuestro documento,
// este comando convertirá en blanco toda el área que especificamos en "field.PostScriptGroup".
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### Ver también

* class [FieldPrint](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldprint/)
* asamblea [Aspose.Words](../../../)


