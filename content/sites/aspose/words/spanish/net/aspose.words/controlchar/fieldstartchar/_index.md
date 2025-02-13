---
title: ControlChar.FieldStartChar
second_title: Referencia de API de Aspose.Words para .NET
description: ControlChar campo. Inicio del carácter de campo de MS Word char19.
type: docs
weight: 100
url: /es/net/aspose.words/controlchar/fieldstartchar/
---
## ControlChar.FieldStartChar field

Inicio del carácter de campo de MS Word: (char)19.

```csharp
public const char FieldStartChar;
```

### Ejemplos

Muestra cómo agregar varios caracteres de control a un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Agrega un espacio regular.
builder.Write("Before space." + ControlChar.SpaceChar + "After space.");

// Agregue un NBSP, que es un espacio que no se divide.
// A diferencia del espacio normal, este espacio no puede tener un salto de línea automático en su posición.
builder.Write("Before space." + ControlChar.NonBreakingSpace + "After space.");

// Agrega un carácter de tabulación.
builder.Write("Before tab." + ControlChar.Tab + "After tab.");

// Agrega un salto de línea.
builder.Write("Before line break." + ControlChar.LineBreak + "After line break.");

// Agrega una nueva línea y comienza un nuevo párrafo.
Assert.AreEqual(1, doc.FirstSection.Body.GetChildNodes(NodeType.Paragraph, true).Count);
builder.Write("Before line feed." + ControlChar.LineFeed + "After line feed.");
Assert.AreEqual(2, doc.FirstSection.Body.GetChildNodes(NodeType.Paragraph, true).Count);

// El carácter de avance de línea tiene dos versiones.
Assert.AreEqual(ControlChar.LineFeed, ControlChar.Lf);

// Los retornos de carro y los saltos de línea se pueden representar juntos por un carácter.
Assert.AreEqual(ControlChar.CrLf, ControlChar.Cr + ControlChar.Lf);

// Agregue un salto de párrafo, que comenzará un nuevo párrafo.
builder.Write("Before paragraph break." + ControlChar.ParagraphBreak + "After paragraph break.");
Assert.AreEqual(3, doc.FirstSection.Body.GetChildNodes(NodeType.Paragraph, true).Count);

// Agregar un salto de sección. Esto no crea una nueva sección o párrafo.
Assert.AreEqual(1, doc.Sections.Count);
builder.Write("Before section break." + ControlChar.SectionBreak + "After section break.");
Assert.AreEqual(1, doc.Sections.Count);

// Agregar un salto de página.
builder.Write("Before page break." + ControlChar.PageBreak + "After page break.");

// Un salto de página tiene el mismo valor que un salto de sección.
Assert.AreEqual(ControlChar.PageBreak, ControlChar.SectionBreak);

// Inserta una nueva sección y luego establece su número de columnas en dos.
doc.AppendChild(new Section(doc));
builder.MoveToSection(1);
builder.CurrentSection.PageSetup.TextColumns.SetCount(2);

// Podemos usar un carácter de control para marcar el punto donde el texto se mueve a la siguiente columna.
builder.Write("Text at end of column 1." + ControlChar.ColumnBreak + "Text at beginning of column 2.");

doc.Save(ArtifactsDir + "ControlChar.InsertControlChars.docx");

// Hay contrapartes char y string para la mayoría de los caracteres.
Assert.AreEqual(Convert.ToChar(ControlChar.Cell), ControlChar.CellChar);
Assert.AreEqual(Convert.ToChar(ControlChar.NonBreakingSpace), ControlChar.NonBreakingSpaceChar);
Assert.AreEqual(Convert.ToChar(ControlChar.Tab), ControlChar.TabChar);
Assert.AreEqual(Convert.ToChar(ControlChar.LineBreak), ControlChar.LineBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.LineFeed), ControlChar.LineFeedChar);
Assert.AreEqual(Convert.ToChar(ControlChar.ParagraphBreak), ControlChar.ParagraphBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.SectionBreak), ControlChar.SectionBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.PageBreak), ControlChar.SectionBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.ColumnBreak), ControlChar.ColumnBreakChar);
```

### Ver también

* class [ControlChar](../)
* espacio de nombres [Aspose.Words](../../controlchar/)
* asamblea [Aspose.Words](../../../)


