---
title: Class FieldToc
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fields.FieldToc clase. Implementa el campo TOC.
type: docs
weight: 2380
url: /es/net/aspose.words.fields/fieldtoc/
---
## FieldToc class

Implementa el campo TOC.

```csharp
public class FieldToc : Field
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [FieldToc](fieldtoc/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [BookmarkName](../../aspose.words.fields/fieldtoc/bookmarkname/) { get; set; } | Obtiene o establece el nombre del marcador que marca la parte del documento utilizada para crear la tabla. |
| [CaptionlessTableOfFiguresLabel](../../aspose.words.fields/fieldtoc/captionlesstableoffigureslabel/) { get; set; } | Obtiene o establece el nombre del identificador de secuencia que se utiliza al crear una tabla de cifras que no incluye la etiqueta y el número del título . |
| [CustomStyles](../../aspose.words.fields/fieldtoc/customstyles/) { get; set; } | Obtiene o establece una lista de estilos distintos de los estilos de encabezado incorporados para incluir en la tabla de contenido. |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | Obtiene el texto que representa el resultado del campo mostrado. |
| [End](../../aspose.words.fields/field/end/) { get; } | Obtiene el nodo que representa el final del campo. |
| [EntryIdentifier](../../aspose.words.fields/fieldtoc/entryidentifier/) { get; set; } | Obtiene o establece una cadena que debe coincidir con los identificadores de tipo de los campos TC que se incluyen. |
| [EntryLevelRange](../../aspose.words.fields/fieldtoc/entrylevelrange/) { get; set; } | Obtiene o establece un rango de niveles de las entradas de la tabla de contenido que se van a incluir. |
| [EntrySeparator](../../aspose.words.fields/fieldtoc/entryseparator/) { get; set; } | Obtiene o establece una secuencia de caracteres que separan una entrada y su número de página. |
| [Format](../../aspose.words.fields/field/format/) { get; } | Obtiene un[`FieldFormat`](../fieldformat/) objeto que proporciona acceso escrito al formato del campo. |
| [HeadingLevelRange](../../aspose.words.fields/fieldtoc/headinglevelrange/) { get; set; } | Obtiene o establece un rango de niveles de encabezado para incluir. |
| [HideInWebLayout](../../aspose.words.fields/fieldtoc/hideinweblayout/) { get; set; } | Obtiene o establece si ocultar el encabezado de la pestaña y los números de página en la vista Diseño web. |
| [InsertHyperlinks](../../aspose.words.fields/fieldtoc/inserthyperlinks/) { get; set; } | Obtiene o establece si se deben hacer hipervínculos en las entradas de la tabla de contenido. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | Obtiene o establece si el resultado actual del campo ya no es correcto (obsoleto) debido a otras modificaciones realizadas en el documento. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | Obtiene o establece si el campo está bloqueado (no debe recalcular su resultado). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | Obtiene o establece el LCID del campo. |
| [PageNumberOmittingLevelRange](../../aspose.words.fields/fieldtoc/pagenumberomittinglevelrange/) { get; set; } | Obtiene o establece un rango de niveles de las entradas de la tabla de contenido de las que omite los números de página. |
| [PrefixedSequenceIdentifier](../../aspose.words.fields/fieldtoc/prefixedsequenceidentifier/) { get; set; } | Obtiene o establece el identificador de una secuencia para la que se debe agregar un prefijo al número de página de la entrada. |
| [PreserveLineBreaks](../../aspose.words.fields/fieldtoc/preservelinebreaks/) { get; set; } | Obtiene o establece si conservar los caracteres de nueva línea dentro de las entradas de la tabla. |
| [PreserveTabs](../../aspose.words.fields/fieldtoc/preservetabs/) { get; set; } | Obtiene o establece si se deben conservar las entradas de la pestaña dentro de las entradas de la tabla. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | Obtiene o establece el texto que se encuentra entre el separador de campo y el final del campo. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | Obtiene el nodo que representa el separador de campos. Puede ser nulo. |
| [SequenceSeparator](../../aspose.words.fields/fieldtoc/sequenceseparator/) { get; set; } | Obtiene o establece la secuencia de caracteres que se utiliza para separar números de secuencia y números de página. |
| [Start](../../aspose.words.fields/field/start/) { get; } | Obtiene el nodo que representa el inicio del campo. |
| [TableOfFiguresLabel](../../aspose.words.fields/fieldtoc/tableoffigureslabel/) { get; set; } | Obtiene o establece el nombre del identificador de secuencia utilizado al construir una tabla de figuras. |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | Obtiene el tipo de campo de Microsoft Word. |
| [UseParagraphOutlineLevel](../../aspose.words.fields/fieldtoc/useparagraphoutlinelevel/) { get; set; } | Obtiene o establece si usar el nivel de esquema de párrafo aplicado. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | Devuelve el texto entre el inicio del campo y el separador de campo (o el final del campo si no hay separador). Se incluyen tanto el código de campo como el resultado de campo de los campos secundarios. |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | Devuelve el texto entre el inicio del campo y el separador de campo (o el final del campo si no hay separador). |
| [Remove](../../aspose.words.fields/field/remove/)() | Elimina el campo del documento. Devuelve un nodo justo después del campo. Si el final del campo es el último hijo de su nodo principal, devuelve su párrafo principal. Si el campo ya está eliminado, devuelve **nulo** . |
| [Unlink](../../aspose.words.fields/field/unlink/)() | Realiza el desvinculado del campo. |
| [Update](../../aspose.words.fields/field/update/)() | Realiza la actualización del campo. Se lanza si el campo ya se está actualizando. |
| [Update](../../aspose.words.fields/field/update/)(bool) | Realiza una actualización de campo. Se lanza si el campo ya se está actualizando. |
| [UpdatePageNumbers](../../aspose.words.fields/fieldtoc/updatepagenumbers/)() | Actualiza los números de página de los elementos de esta tabla de contenido. |

### Observaciones

Construye una tabla de contenido (que también puede ser una tabla de figuras) utilizando las entradas especificadas por los campos TC, sus niveles de encabezado y estilos especificados, e inserta esa tabla en este lugar del documento.

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

Muestra cómo llenar un campo TOC con entradas usando campos SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Un campo TOC puede crear una entrada en su tabla de contenido para cada campo SEQ encontrado en el documento.
// Cada entrada contiene el párrafo que incluye el campo SEQ y el número de página en el que aparece el campo.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

// Los campos SEQ muestran un recuento que se incrementa en cada campo SEQ.
// Estos campos también mantienen cuentas separadas para cada secuencia nombrada única
// identificado por la propiedad "SequenceIdentifier" del campo SEQ.
// Use la propiedad "TableOfFiguresLabel" para nombrar una secuencia principal para el TOC.
// Ahora, este TOC solo creará entradas a partir de campos SEQ con su "Identificador de secuencia" establecido en "Mi secuencia".
fieldToc.TableOfFiguresLabel = "MySequence";

// Podemos nombrar otra secuencia de campo SEQ en la propiedad "PrefixedSequenceIdentifier".
  // Los campos SEQ de esta secuencia de prefijos no crearán entradas TOC.
// Cada entrada TOC creada a partir de un campo SEQ de secuencia principal ahora también mostrará el recuento que
// la secuencia de prefijo se encuentra actualmente en el campo SEQ de secuencia principal que realizó la entrada.
fieldToc.PrefixedSequenceIdentifier = "PrefixSequence";

// Cada entrada de TOC mostrará el conteo de secuencia de prefijo inmediatamente a la izquierda
// del número de página en el que aparece el campo SEQ de la secuencia principal.
// Podemos especificar un separador personalizado que aparecerá entre estos dos números.
fieldToc.SequenceSeparator = ">";

Assert.AreEqual(" TOC  \\c MySequence \\s PrefixSequence \\d >", fieldToc.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);

// Hay dos formas de usar los campos SEQ para completar este TOC.
// 1 - Insertar un campo SEQ que pertenece a la secuencia de prefijos del TOC:
// Este campo incrementará el recuento de secuencias SEQ para "PrefixSequence" en 1.
// Dado que este campo no pertenece a la secuencia principal identificada
// por la propiedad "TableOfFiguresLabel" del TOC, no aparecerá como entrada.
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();

Assert.AreEqual(" SEQ  PrefixSequence", fieldSeq.GetFieldCode());

// 2 - Insertar un campo SEQ que pertenezca a la secuencia principal del TOC:
// Este campo SEQ creará una entrada en la TOC.
// La entrada TOC contendrá el párrafo en el que se encuentra el campo SEQ y el número de la página en la que aparece.
// Esta entrada también mostrará el recuento en el que se encuentra actualmente la secuencia de prefijos,
// separado del número de página por el valor de la propiedad SeqenceSeparator de la tabla de contenido.
// El recuento de "PrefixSequence" está en 1, este campo SEQ de secuencia principal está en la página 2,
// y el separador es ">", por lo que la entrada mostrará "1>2".
builder.Write("First TOC entry, MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", fieldSeq.GetFieldCode());

// Inserte una página, avance la secuencia del prefijo en 2 e inserte un campo SEQ para crear una entrada TOC después.
// La secuencia del prefijo ahora está en 2, y el campo SEQ de la secuencia principal está en la página 3,
// por lo que la entrada TOC mostrará "2>3" en su recuento de páginas.
builder.InsertBreak(BreakType.PageBreak);
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
builder.Write("Second TOC entry, MySequence #");
fieldSeq.SequenceIdentifier = "MySequence";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TOC.SEQ.docx");
```

### Ver también

* class [Field](../field/)
* espacio de nombres [Aspose.Words.Fields](../../aspose.words.fields/)
* asamblea [Aspose.Words](../../)


