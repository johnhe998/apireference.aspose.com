---
title: FieldRef.InsertParagraphNumberInRelativeContext
second_title: Referencia de API de Aspose.Words para .NET
description: FieldRef propiedad. Obtiene o establece si insertar el número de párrafo del párrafo al que se hace referencia en contexto relativo.
type: docs
weight: 70
url: /es/net/aspose.words.fields/fieldref/insertparagraphnumberinrelativecontext/
---
## FieldRef.InsertParagraphNumberInRelativeContext property

Obtiene o establece si insertar el número de párrafo del párrafo al que se hace referencia en contexto relativo.

```csharp
public bool InsertParagraphNumberInRelativeContext { get; set; }
```

### Ejemplos

Muestra cómo insertar campos REF en marcadores de referencia.

```csharp
public void FieldRef()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");
    builder.InsertFootnote(FootnoteType.Footnote, "MyBookmark footnote #1");
    builder.Write("Text that will appear in REF field");
    builder.InsertFootnote(FootnoteType.Footnote, "MyBookmark footnote #2");
    builder.EndBookmark("MyBookmark");
    builder.MoveToDocumentStart();

    // Aplicaremos un formato de lista personalizado, donde la cantidad de paréntesis angulares indica el nivel de lista en el que nos encontramos actualmente.
    builder.ListFormat.ApplyNumberDefault();
    builder.ListFormat.ListLevel.NumberFormat = "> \x0000";

    // Inserte un campo REF que contendrá el texto dentro de nuestro marcador, actuará como un hipervínculo y clonará las notas al pie del marcador.
    FieldRef field = InsertFieldRef(builder, "MyBookmark", "", "\n");
    field.IncludeNoteOrComment = true;
    field.InsertHyperlink = true;

    Assert.AreEqual(" REF  MyBookmark \\f \\h", field.GetFieldCode());

    // Inserta un campo REF y muestra si el marcador al que se hace referencia está encima o debajo de él.
    field = InsertFieldRef(builder, "MyBookmark", "The referenced paragraph is ", " this field.\n");
    field.InsertRelativePosition = true;

    Assert.AreEqual(" REF  MyBookmark \\p", field.GetFieldCode());

    // Muestra el número de lista del marcador tal como aparece en el documento.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's paragraph number is ", "\n");
    field.InsertParagraphNumber = true;

    Assert.AreEqual(" REF  MyBookmark \\n", field.GetFieldCode());

    // Mostrar el número de lista del marcador, pero con caracteres no delimitadores, como los corchetes angulares, omitidos.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's paragraph number, non-delimiters suppressed, is ", "\n");
    field.InsertParagraphNumber = true;
    field.SuppressNonDelimiters = true;

    Assert.AreEqual(" REF  MyBookmark \\n \\t", field.GetFieldCode());

    // Bajar un nivel de lista.
    builder.ListFormat.ListLevelNumber++;
    builder.ListFormat.ListLevel.NumberFormat = ">> \x0001";

    // Mostrar el número de lista del marcador y los números de todos los niveles de lista por encima de él.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's full context paragraph number is ", "\n");
    field.InsertParagraphNumberInFullContext = true;

    Assert.AreEqual(" REF  MyBookmark \\w", field.GetFieldCode());

    builder.InsertBreak(BreakType.PageBreak);

    // Mostrar los números de nivel de lista entre este campo REF y el marcador al que hace referencia.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's relative paragraph number is ", "\n");
    field.InsertParagraphNumberInRelativeContext = true;

    Assert.AreEqual(" REF  MyBookmark \\r", field.GetFieldCode());

    // Al final del documento, el marcador aparecerá aquí como un elemento de la lista.
    builder.Writeln("List level above bookmark");
    builder.ListFormat.ListLevelNumber++;
    builder.ListFormat.ListLevel.NumberFormat = ">>> \x0002";

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.REF.docx");

/// <summary>
/// Obtener el generador de documentos para insertar un campo REF, hacer referencia a un marcador con él y agregar texto antes y después.
/// </summary>
private static FieldRef InsertFieldRef(DocumentBuilder builder, string bookmarkName, string textBefore, string textAfter)
{
    builder.Write(textBefore);
    FieldRef field = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
    field.BookmarkName = bookmarkName;
    builder.Write(textAfter);
    return field;
}
```

### Ver también

* class [FieldRef](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldref/)
* asamblea [Aspose.Words](../../../)


