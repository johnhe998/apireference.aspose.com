---
title: MailMerge.UseWholeParagraphAsRegion
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge propiedad. Obtiene o establece un valor que indica si el párrafo completo con el campo TableStart o TableEnd o un rango particular entre los campos TableStart y TableEnd debe incluirse en la región de combinación de correspondencia.
type: docs
weight: 160
url: /es/net/aspose.words.mailmerging/mailmerge/usewholeparagraphasregion/
---
## MailMerge.UseWholeParagraphAsRegion property

Obtiene o establece un valor que indica si el párrafo completo con el campo TableStart o TableEnd o un rango particular entre los campos TableStart y TableEnd debe incluirse en la región de combinación de correspondencia.

```csharp
public bool UseWholeParagraphAsRegion { get; set; }
```

### Observaciones

El valor predeterminado es **verdadero** .

### Ejemplos

Muestra la relación entre las regiones de combinación de correspondencia y los párrafos.

```csharp
public void UseWholeParagraphAsRegion(bool useWholeParagraphAsRegion)
{
    Document doc = CreateSourceDocWithNestedMergeRegions();
    DataTable dataTable = CreateSourceTableDataTableForOneRegion();

    // De forma predeterminada, un párrafo no puede pertenecer a más de una región de combinación de correspondencia.
    // El contenido de nuestro documento no cumple con estos criterios.
    // Si establecemos el indicador "UseWholeParagraphAsRegion" en "true",
    // ejecutar una combinación de correspondencia en este documento generará una excepción.
    // Si establecemos el indicador "UseWholeParagraphAsRegion" en "falso",
    // podremos ejecutar una combinación de correspondencia en este documento.
    doc.MailMerge.UseWholeParagraphAsRegion = useWholeParagraphAsRegion;

    if (useWholeParagraphAsRegion)
        Assert.Throws<InvalidOperationException>(() => doc.MailMerge.ExecuteWithRegions(dataTable));
    else
        doc.MailMerge.ExecuteWithRegions(dataTable);

    // La combinación de correspondencia llena nuestra primera región mientras deja la segunda región sin usar
    // ya que es la región la que rompe la regla.
    doc.Save(ArtifactsDir + "MailMerge.UseWholeParagraphAsRegion.docx");
}

/// <summary>
/// Cree un documento con dos regiones de combinación de correspondencia que comparten un párrafo.
/// </summary>
private static Document CreateSourceDocWithNestedMergeRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Write("Region 1: ");
    builder.InsertField(" MERGEFIELD TableStart:MyTable");
    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column2");
    builder.InsertField(" MERGEFIELD TableEnd:MyTable");

    builder.Write(", Region 2: ");
    builder.InsertField(" MERGEFIELD TableStart:MyOtherTable");
    builder.InsertField(" MERGEFIELD TableEnd:MyOtherTable");

    return doc;
}

/// <summary>
/// Cree una tabla de datos que pueda llenar una región durante una combinación de correspondencia.
/// </summary>
private static DataTable CreateSourceTableDataTableForOneRegion()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value 1", "Value 2" });

    return dataTable;
}
```

### Ver también

* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


