---
title: FootnoteOptions.NumberStyle
second_title: Referencia de API de Aspose.Words para .NET
description: FootnoteOptions propiedad. Especifica el formato de número para las notas al pie numeradas automáticamente.
type: docs
weight: 20
url: /es/net/aspose.words.notes/footnoteoptions/numberstyle/
---
## FootnoteOptions.NumberStyle property

Especifica el formato de número para las notas al pie numeradas automáticamente.

```csharp
public NumberStyle NumberStyle { get; set; }
```

### Observaciones

No todos los estilos de números son aplicables a esta propiedad. Para ver la lista de estilos numéricos aplicables , consulte el cuadro de diálogo Insertar nota al pie o nota al final en Microsoft Word. Si selecciona un estilo de número que no es aplicable, Microsoft Word volverá a un valor predeterminado.

### Ejemplos

Muestra cómo cambiar el estilo numérico de las marcas de referencia de notas al pie/notas al final.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Las notas al pie y las notas al final son una forma de adjuntar una referencia o un comentario al margen del texto
// que no interfiere con el flujo del texto del cuerpo principal. 
// Insertar una nota al pie/nota al final agrega un pequeño símbolo de referencia en superíndice
// en el texto del cuerpo principal donde insertamos la nota al pie/nota al final.
// Cada nota al pie/nota al final también crea una entrada, que consta de un símbolo que coincide con la referencia
// símbolo en el texto del cuerpo principal. El texto de referencia que pasamos al método "InsertEndnote" del generador de documentos.
// Las entradas de notas al pie, por defecto, aparecen en la parte inferior de cada página que contiene
// sus símbolos de referencia y notas al final se muestran al final del documento.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.", "Custom footnote reference mark");

builder.InsertParagraph();

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.", "Custom endnote reference mark");

// Por defecto, el símbolo de referencia para cada nota al pie y al final es su índice
// entre todas las notas al pie/notas al final del documento. Cada documento mantiene cuentas separadas
// para notas al pie y notas al final. De forma predeterminada, las notas al pie muestran sus números usando números arábigos,
// y las notas finales muestran sus números en números romanos en minúsculas.
Assert.AreEqual(NumberStyle.Arabic, doc.FootnoteOptions.NumberStyle);
Assert.AreEqual(NumberStyle.LowercaseRoman, doc.EndnoteOptions.NumberStyle);

// Podemos usar la propiedad "NumberStyle" para aplicar estilos de numeración personalizados a las notas al pie y al final.
// Esto no afectará las notas al pie/notas al final con marcas de referencia personalizadas.
doc.FootnoteOptions.NumberStyle = NumberStyle.UppercaseRoman;
doc.EndnoteOptions.NumberStyle = NumberStyle.UppercaseLetter;

doc.Save(ArtifactsDir + "InlineStory.RefMarkNumberStyle.docx");
```

### Ver también

* enum [NumberStyle](../../../aspose.words/numberstyle/)
* class [FootnoteOptions](../)
* espacio de nombres [Aspose.Words.Notes](../../footnoteoptions/)
* asamblea [Aspose.Words](../../../)


