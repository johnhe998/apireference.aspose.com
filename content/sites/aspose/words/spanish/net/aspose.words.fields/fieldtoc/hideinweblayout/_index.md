---
title: FieldToc.HideInWebLayout
second_title: Referencia de API de Aspose.Words para .NET
description: FieldToc propiedad. Obtiene o establece si ocultar el encabezado de la pestaña y los números de página en la vista Diseño web.
type: docs
weight: 90
url: /es/net/aspose.words.fields/fieldtoc/hideinweblayout/
---
## FieldToc.HideInWebLayout property

Obtiene o establece si ocultar el encabezado de la pestaña y los números de página en la vista Diseño web.

```csharp
public bool HideInWebLayout { get; set; }
```

### Ejemplos

Muestra cómo insertar una TOC y llenarla con entradas basadas en estilos de títulos.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");

    // Inserte un campo TOC, que compilará todos los encabezados en una tabla de contenido.
    // Para cada encabezado, este campo creará una línea con el texto en ese estilo de encabezado a la izquierda,
    // y la página en la que aparece el encabezado a la derecha.
    FieldToc field = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

    // Usa la propiedad BookmarkName para enumerar solo los encabezados
    // que aparecen dentro de los límites de un marcador con el nombre "MyBookmark".
    field.BookmarkName = "MyBookmark";

    // El texto con un estilo de encabezado incorporado, como "Título 1", aplicado al mismo contará como un encabezado.
    // Podemos nombrar estilos adicionales para que el TOC los recoja como encabezados en esta propiedad y sus niveles de TOC.
    field.CustomStyles = "Quote; 6; Intense Quote; 7";

    // Por defecto, los niveles de Estilos/TOC están separados en la propiedad CustomStyles por una coma,
    // pero podemos establecer un delimitador personalizado en esta propiedad.
    doc.FieldOptions.CustomTocStyleSeparator = ";";

    // Configure el campo para excluir cualquier encabezado que tenga niveles de TOC fuera de este rango.
    field.HeadingLevelRange = "1-3";

    // El TOC no mostrará los números de página de los encabezados cuyos niveles de TOC estén dentro de este rango.
    field.PageNumberOmittingLevelRange = "2-5";

      // Establecer una cadena personalizada que separará cada encabezado de su número de página.
    field.EntrySeparator = "-";
    field.InsertHyperlinks = true;
    field.HideInWebLayout = false;
    field.PreserveLineBreaks = true;
    field.PreserveTabs = true;
    field.UseParagraphOutlineLevel = false;

    InsertNewPageWithHeading(builder, "First entry", "Heading 1");
    builder.Writeln("Paragraph text.");
    InsertNewPageWithHeading(builder, "Second entry", "Heading 1");
    InsertNewPageWithHeading(builder, "Third entry", "Quote");
    InsertNewPageWithHeading(builder, "Fourth entry", "Intense Quote");

    // Estos dos encabezados tendrán los números de página omitidos porque están dentro del rango "2-5".
    InsertNewPageWithHeading(builder, "Fifth entry", "Heading 2");
    InsertNewPageWithHeading(builder, "Sixth entry", "Heading 3");

    // Esta entrada no aparece porque "Título 4" está fuera del rango "1-3" que hemos establecido anteriormente.
    InsertNewPageWithHeading(builder, "Seventh entry", "Heading 4");

    builder.EndBookmark("MyBookmark");
    builder.Writeln("Paragraph text.");

    // Esta entrada no aparece porque está fuera del marcador especificado por el TOC.
    InsertNewPageWithHeading(builder, "Eighth entry", "Heading 1");

    Assert.AreEqual(" TOC  \\b MyBookmark \\t \"Quote; 6; Intense Quote; 7\" \\o 1-3 \\n 2-5 \\p - \\h \\x \\w", field.GetFieldCode());

    field.UpdatePageNumbers();
    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.TOC.docx");

/// <summary>
/// Comienza una nueva página e inserta un párrafo de un estilo específico.
/// </summary>
public void InsertNewPageWithHeading(DocumentBuilder builder, string captionText, string styleName)
{
    builder.InsertBreak(BreakType.PageBreak);
    string originalStyle = builder.ParagraphFormat.StyleName;
    builder.ParagraphFormat.Style = builder.Document.Styles[styleName];
    builder.Writeln(captionText);
    builder.ParagraphFormat.Style = builder.Document.Styles[originalStyle];
}
```

### Ver también

* class [FieldToc](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldtoc/)
* asamblea [Aspose.Words](../../../)


