---
title: EndnoteOptions.Position
second_title: Referencia de API de Aspose.Words para .NET
description: EndnoteOptions propiedad. Especifica la posición de las notas al final.
type: docs
weight: 20
url: /es/net/aspose.words.notes/endnoteoptions/position/
---
## EndnoteOptions.Position property

Especifica la posición de las notas al final.

```csharp
public EndnotePosition Position { get; set; }
```

### Ejemplos

Muestra cómo seleccionar un lugar diferente donde el documento recopila y muestra sus notas al final.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Una nota al final es una forma de adjuntar una referencia o un comentario al margen del texto
// que no interfiere con el flujo del texto del cuerpo principal. 
// Insertar una nota al final agrega un pequeño símbolo de referencia de superíndice
// en el texto del cuerpo principal donde insertamos la nota final.
// Cada nota al final también crea una entrada al final del documento, que consta de un símbolo
// que coincide con el símbolo de referencia en el texto del cuerpo principal.
// El texto de referencia que pasamos al método "InsertEndnote" del generador de documentos.
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote contents.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("This is the second section.");

// Podemos usar la propiedad "Posición" para determinar dónde colocará el documento todas sus notas al final.
// Si establecemos el valor de la propiedad "Posición" en "EndnotePosition.EndOfDocument",
// cada nota al pie aparecerá en una colección al final del documento. Este es el valor predeterminado.
// Si establecemos el valor de la propiedad "Posición" en "EndnotePosition.EndOfSection",
// cada nota al pie aparecerá en una colección al final de la sección cuyo texto contiene la marca de referencia de la nota al final.
doc.EndnoteOptions.Position = endnotePosition;

doc.Save(ArtifactsDir + "InlineStory.PositionEndnote.docx");
```

### Ver también

* enum [EndnotePosition](../../endnoteposition/)
* class [EndnoteOptions](../)
* espacio de nombres [Aspose.Words.Notes](../../endnoteoptions/)
* asamblea [Aspose.Words](../../../)


