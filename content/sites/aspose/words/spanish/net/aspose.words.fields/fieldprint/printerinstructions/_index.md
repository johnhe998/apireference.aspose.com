---
title: FieldPrint.PrinterInstructions
second_title: Referencia de API de Aspose.Words para .NET
description: FieldPrint propiedad. Obtiene o establece los caracteres del código de control o instrucciones PostScript específicos de la impresora.
type: docs
weight: 30
url: /es/net/aspose.words.fields/fieldprint/printerinstructions/
---
## FieldPrint.PrinterInstructions property

Obtiene o establece los caracteres del código de control o instrucciones PostScript específicos de la impresora.

```csharp
public string PrinterInstructions { get; set; }
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


