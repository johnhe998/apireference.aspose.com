---
title: FootnoteOptions.Position
second_title: Referencia de API de Aspose.Words para .NET
description: FootnoteOptions propiedad. Especifica la posición de las notas al pie.
type: docs
weight: 30
url: /es/net/aspose.words.notes/footnoteoptions/position/
---
## FootnoteOptions.Position property

Especifica la posición de las notas al pie.

```csharp
public FootnotePosition Position { get; set; }
```

### Ejemplos

Muestra cómo seleccionar un lugar diferente donde el documento recopila y muestra sus notas al pie.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Una nota al pie es una forma de adjuntar una referencia o un comentario al margen del texto
// que no interfiere con el flujo del texto del cuerpo principal.  
// Insertar una nota al pie agrega un pequeño símbolo de referencia en superíndice
// en el texto del cuerpo principal donde insertamos la nota al pie.
// Cada nota al pie también crea una entrada en la parte inferior de la página, que consta de un símbolo
// que coincide con el símbolo de referencia en el texto del cuerpo principal.
// El texto de referencia que pasamos al método "InsertFootnote" del generador de documentos.
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote contents.");

// Podemos usar la propiedad "Posición" para determinar dónde colocará el documento todas sus notas al pie.
// Si establecemos el valor de la propiedad "Posición" en "FootnotePosition.BottomOfPage",
// cada nota al pie se mostrará en la parte inferior de la página que contiene su marca de referencia. Este es el valor predeterminado.
// Si establecemos el valor de la propiedad "Posición" en "FootnotePosition.BeneathText",
// cada nota al pie aparecerá al final del texto de la página que contiene su marca de referencia.
doc.FootnoteOptions.Position = footnotePosition;

doc.Save(ArtifactsDir + "InlineStory.PositionFootnote.docx");
```

### Ver también

* enum [FootnotePosition](../../footnoteposition/)
* class [FootnoteOptions](../)
* espacio de nombres [Aspose.Words.Notes](../../footnoteoptions/)
* asamblea [Aspose.Words](../../../)


