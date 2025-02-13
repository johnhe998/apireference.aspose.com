---
title: MailMerge.MergeWholeDocument
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge propiedad. Obtiene o establece un valor que indica si los campos de todo el documento se actualizan al ejecutar una combinación de correspondencia con regiones.
type: docs
weight: 70
url: /es/net/aspose.words.mailmerging/mailmerge/mergewholedocument/
---
## MailMerge.MergeWholeDocument property

Obtiene o establece un valor que indica si los campos de todo el documento se actualizan al ejecutar una combinación de correspondencia con regiones.

```csharp
public bool MergeWholeDocument { get; set; }
```

### Observaciones

El valor predeterminado es **falso** .

### Ejemplos

Muestra la relación entre las combinaciones de correspondencia con las regiones y la actualización de campos.

```csharp
public void MergeWholeDocument(bool mergeWholeDocument)
{
    Document doc = CreateSourceDocMergeWholeDocument();
    DataTable dataTable = CreateSourceTableMergeWholeDocument();

    // Si establecemos el indicador "MergeWholeDocument" en "true",
    // la combinación de correspondencia con las regiones actualizará todos los campos del documento.
    // Si configuramos el indicador "MergeWholeDocument" en "falso", la combinación de correspondencia solo actualizará los campos
    // dentro de la región de combinación de correo cuyo nombre coincide con el nombre de la tabla de origen de datos.
    doc.MailMerge.MergeWholeDocument = mergeWholeDocument;
    doc.MailMerge.ExecuteWithRegions(dataTable);

    // La combinación de correspondencia solo actualizará el campo QUOTE fuera de la región de combinación de correspondencia
    // si establecemos el indicador "MergeWholeDocument" en "true".
    doc.Save(ArtifactsDir + "MailMerge.MergeWholeDocument.docx");

    Assert.True(doc.GetText().Contains("This QUOTE field is inside the \"MyTable\" merge region."));
    Assert.AreEqual(mergeWholeDocument, 
        doc.GetText().Contains("This QUOTE field is outside of the \"MyTable\" merge region."));
}

/// <summary>
/// Cree un documento con una región de combinación de correspondencia que pertenezca a una fuente de datos llamada "MiTabla".
/// Inserte un campo COTIZACIÓN dentro de esta región y uno más fuera de ella.
/// </summary>
private static Document CreateSourceDocMergeWholeDocument()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    FieldQuote field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
    field.Text = "This QUOTE field is outside of the \"MyTable\" merge region.";

    builder.InsertParagraph();
    builder.InsertField(" MERGEFIELD TableStart:MyTable");

    field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
    field.Text = "This QUOTE field is inside the \"MyTable\" merge region.";
    builder.InsertParagraph();

    builder.InsertField(" MERGEFIELD MyColumn");
    builder.InsertField(" MERGEFIELD TableEnd:MyTable");

    return doc;
}

/// <summary>
/// Cree una tabla de datos que se usará en una combinación de correspondencia.
/// </summary>
private static DataTable CreateSourceTableMergeWholeDocument()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("MyColumn");
    dataTable.Rows.Add(new object[] { "MyValue" });

    return dataTable;
}
```

### Ver también

* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


