---
title: Enum FootnoteNumberingRule
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Notes.FootnoteNumberingRule enumeración. Determina cuándo se reinicia la numeración automática de notas al pie o al final.
type: docs
weight: 4030
url: /es/net/aspose.words.notes/footnotenumberingrule/
---
## FootnoteNumberingRule enumeration

Determina cuándo se reinicia la numeración automática de notas al pie o al final.

```csharp
public enum FootnoteNumberingRule
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Continuous | `0` | Numeración continua en todo el documento. |
| RestartSection | `1` | La numeración se reinicia en cada sección. |
| RestartPage | `2` | La numeración se reinicia en cada página. Válido solo para notas al pie. |
| Default | `0` | IgualContinuous . |

### Ejemplos

Muestra cómo reiniciar la numeración de notas al pie/notas al final en ciertos lugares del documento.

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
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 4.");

builder.InsertBreak(BreakType.PageBreak);

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 4.");

// Por defecto, el símbolo de referencia para cada nota al pie y al final es su índice
// entre todas las notas al pie/notas al final del documento. Cada documento mantiene cuentas separadas
// para notas al pie y notas al final y no reinicia estos conteos en ningún momento.
Assert.AreEqual(doc.FootnoteOptions.RestartRule, FootnoteNumberingRule.Default);
Assert.AreEqual(FootnoteNumberingRule.Default, FootnoteNumberingRule.Continuous);

// Podemos usar la propiedad "RestartRule" para que el documento se reinicie
// la nota al pie/nota al final cuenta en una nueva página o sección.
doc.FootnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
doc.EndnoteOptions.RestartRule = FootnoteNumberingRule.RestartSection;

doc.Save(ArtifactsDir + "InlineStory.NumberingRule.docx");
```

### Ver también

* class [FootnoteOptions](../footnoteoptions/)
* class [EndnoteOptions](../endnoteoptions/)
* espacio de nombres [Aspose.Words.Notes](../../aspose.words.notes/)
* asamblea [Aspose.Words](../../)


