---
title: FieldAdvance.RightOffset
second_title: Referencia de API de Aspose.Words para .NET
description: FieldAdvance propiedad. Obtiene o establece el número de puntos por los que el texto que sigue al campo debe moverse hacia la derecha.
type: docs
weight: 50
url: /es/net/aspose.words.fields/fieldadvance/rightoffset/
---
## FieldAdvance.RightOffset property

Obtiene o establece el número de puntos por los que el texto que sigue al campo debe moverse hacia la derecha.

```csharp
public string RightOffset { get; set; }
```

### Ejemplos

Muestra cómo insertar un campo ADVANCE y editar sus propiedades.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This text is in its normal place.");

// A continuación se muestran dos formas de usar el campo ADVANCE para ajustar la posición del texto que lo sigue.
// Los efectos de un campo ADVANCE continúan aplicándose hasta que finaliza el párrafo,
// u otro campo ADVANCE actualiza los valores de desplazamiento/coordenada.
// 1 - Especifique un desplazamiento direccional:
FieldAdvance field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.RightOffset = "5";
field.UpOffset = "5";

Assert.AreEqual(" ADVANCE  \\r 5 \\u 5", field.GetFieldCode());

builder.Write("This text will be moved up and to the right.");

field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.DownOffset = "5";
field.LeftOffset = "100";

Assert.AreEqual(" ADVANCE  \\d 5 \\l 100", field.GetFieldCode());

builder.Writeln("This text is moved down and to the left, overlapping the previous text.");

// 2 - Mover texto a una posición especificada por coordenadas:
field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.HorizontalPosition = "-100";
field.VerticalPosition = "200";

Assert.AreEqual(" ADVANCE  \\x -100 \\y 200", field.GetFieldCode());

builder.Write("This text is in a custom position.");

doc.Save(ArtifactsDir + "Field.ADVANCE.docx");
```

### Ver también

* class [FieldAdvance](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldadvance/)
* asamblea [Aspose.Words](../../../)


