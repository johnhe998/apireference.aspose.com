---
title: FootnoteOptions.StartNumber
second_title: Referencia de API de Aspose.Words para .NET
description: FootnoteOptions propiedad. Especifica el número o carácter inicial para las primeras notas al pie numeradas automáticamente.
type: docs
weight: 50
url: /es/net/aspose.words.notes/footnoteoptions/startnumber/
---
## FootnoteOptions.StartNumber property

Especifica el número o carácter inicial para las primeras notas al pie numeradas automáticamente.

```csharp
public int StartNumber { get; set; }
```

### Observaciones

Esta propiedad tiene efecto sólo cuando[`RestartRule`](../restartrule/) se establece en Continuous.

### Ejemplos

Muestra cómo establecer un número en el que el documento comienza el recuento de notas al pie/notas al final.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Las notas al pie y las notas al final son una forma de adjuntar una referencia o un comentario al margen del texto
// que no interfiere con el flujo del texto del cuerpo principal. 
// Insertar una nota al pie/nota al final agrega un pequeño símbolo de referencia en superíndice
// en el texto del cuerpo principal donde insertamos la nota al pie/nota al final.
// Cada nota al pie/nota al final también crea una entrada, que consta de un símbolo
// que coincide con el símbolo de referencia en el texto del cuerpo principal.
// El texto de referencia que pasamos al método "InsertEndnote" del generador de documentos.
// Las entradas de notas al pie, por defecto, aparecen en la parte inferior de cada página que contiene
// sus símbolos de referencia y notas al final se muestran al final del documento.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");

builder.InsertParagraph();

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");

// Por defecto, el símbolo de referencia para cada nota al pie y al final es su índice
// entre todas las notas al pie/notas al final del documento. Cada documento mantiene cuentas separadas
// para notas al pie y notas al final, que comienzan en 1.
Assert.AreEqual(1, doc.FootnoteOptions.StartNumber);
Assert.AreEqual(1, doc.EndnoteOptions.StartNumber);

// Podemos usar la propiedad "StartNumber" para obtener el documento
// comienza un conteo de notas al pie o al final en un número diferente.
doc.EndnoteOptions.NumberStyle = NumberStyle.Arabic;
doc.EndnoteOptions.StartNumber = 50;

doc.Save(ArtifactsDir + "InlineStory.StartNumber.docx");
```

### Ver también

* class [FootnoteOptions](../)
* espacio de nombres [Aspose.Words.Notes](../../footnoteoptions/)
* asamblea [Aspose.Words](../../../)


