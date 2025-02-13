---
title: Enum FootnoteType
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Notes.FootnoteType enumeración. Especifica si se trata de una nota al pie o al final.
type: docs
weight: 4060
url: /es/net/aspose.words.notes/footnotetype/
---
## FootnoteType enumeration

Especifica si se trata de una nota al pie o al final.

```csharp
public enum FootnoteType
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Footnote | `0` | El objeto es una nota al pie. |
| Endnote | `1` | El objeto es una nota al final. |

### Observaciones

Tanto las notas al pie como las notas al final están representadas por objetos mediante elFootnote clase . Usar[`FootnoteType`](../footnote/footnotetype/) para distinguir entre notas al pie y notas al final.

### Ejemplos

Muestra cómo hacer referencia al texto con una nota al pie y una nota al final.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte texto y márquelo con una nota al pie con la propiedad IsAuto establecida en "true" de forma predeterminada,
// por lo que el marcador que se ve en el cuerpo del texto se numerará automáticamente en "1",
// y la nota al pie aparecerá en la parte inferior de la página.
builder.Write("This text will be referenced by a footnote.");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote comment regarding referenced text.");

// Inserta más texto y márcalo con una nota al final con una marca de referencia personalizada,
// que se usará en lugar del número "2" y establecerá "IsAuto" en falso.
builder.Write("This text will be referenced by an endnote.");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote comment regarding referenced text.", "CustomMark");

// Las notas al pie siempre aparecen en la parte inferior de su texto de referencia,
// para que este salto de página no afecte la nota al pie.
// Por otro lado, las notas al final siempre están al final del documento
// para que este salto de página empuje la nota final hacia la página siguiente.
builder.InsertBreak(BreakType.PageBreak);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertFootnote.docx");
```

Muestra cómo insertar y personalizar notas al pie.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Agregue texto y haga referencia a él con una nota al pie. Esta nota al pie colocará una pequeña referencia en superíndice
// marca después del texto al que hace referencia y crea una entrada debajo del texto del cuerpo principal en la parte inferior de la página.
// Esta entrada contendrá la marca de referencia de la nota al pie y el texto de referencia,
// que pasaremos al método "InsertFootnote" del generador de documentos.
builder.Write("Main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Si esta propiedad se establece en "verdadero", entonces la marca de referencia de nuestra nota al pie
// será su índice entre todas las notas a pie de página de la sección.
// Esta es la primera nota al pie, por lo que la marca de referencia será "1".
Assert.True(footnote.IsAuto);

// Podemos mover el generador de documentos dentro de la nota al pie para editar su texto de referencia. 
builder.MoveTo(footnote.FirstParagraph);
builder.Write(" More text added by a DocumentBuilder.");
builder.MoveToDocumentEnd();

Assert.AreEqual("\u0002 Footnote text. More text added by a DocumentBuilder.", footnote.GetText().Trim());

builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Podemos establecer una marca de referencia personalizada que utilizará la nota al pie en lugar de su número de índice.
footnote.ReferenceMark = "RefMark";

Assert.False(footnote.IsAuto);

// Un marcador con el indicador "IsAuto" establecido en verdadero seguirá mostrando su índice real
// incluso si los marcadores anteriores muestran marcas de referencia personalizadas, la marca de referencia de este marcador será un "3".
builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

Assert.True(footnote.IsAuto);

doc.Save(ArtifactsDir + "InlineStory.AddFootnote.docx");
```

### Ver también

* espacio de nombres [Aspose.Words.Notes](../../aspose.words.notes/)
* asamblea [Aspose.Words](../../)


