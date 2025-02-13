---
title: MailMerge.UseNonMergeFields
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge propiedad. Cuando es verdadero especifica que además de los campos MERGEFIELD la combinación de correspondencia se realiza en algunos otros tipos de campos y también en las etiquetas fieldName.
type: docs
weight: 150
url: /es/net/aspose.words.mailmerging/mailmerge/usenonmergefields/
---
## MailMerge.UseNonMergeFields property

Cuando es verdadero, especifica que además de los campos MERGEFIELD, la combinación de correspondencia se realiza en algunos otros tipos de campos y también en las etiquetas "{{fieldName}}".

```csharp
public bool UseNonMergeFields { get; set; }
```

### Observaciones

Normalmente, la combinación de correspondencia solo se realiza en campos MERGEFIELD, pero varios clientes crearon su reporting usando otros campos y crearon muchos documentos de esta manera. Para simplificar la migración (y debido a que varios clientes utilizaron este enfoque de forma independiente), se introdujo la capacidad de combinar correspondencia en otros campos.

Cuando **UseNonMergeFieldsUseNonMergeFields** se establece en verdadero, Aspose.Words realizará la combinación de correspondencia en los siguientes campos:

MERGEFIELD Nombre de campo

MACROBOTÓN NOMACRO Nombre del campo

SI 0 = 0 "{Nombre del campo}" ""

Además, cuando **UsuarioNonMergeFieldsUsuarioNonMergeFields** se establece en verdadero, Aspose.Words realizará la combinación de correspondencia en las etiquetas de texto "{{fieldName}}". Estos no son campos, sino solo etiquetas de texto.

### Ejemplos

Muestra cómo conservar la apariencia de las etiquetas de combinación de correspondencia alternativas que no se usan durante una combinación de correspondencia.

```csharp
public void PreserveUnusedTags(bool preserveUnusedTags)
{
    Document doc = CreateSourceDocWithAlternativeMergeFields();
    DataTable dataTable = CreateSourceTablePreserveUnusedTags();

    // De forma predeterminada, una combinación de correspondencia coloca datos de cada fila de una tabla en MERGEFIELD, que nombran columnas en esa tabla. 
    // Nuestro documento no tiene tales campos, pero tiene etiquetas de texto sin formato encerradas entre llaves.
    // Si configuramos el indicador "PreserveUnusedTags" en "true", podríamos tratar estas etiquetas como MERGEFIELD
    // para permitir que nuestra combinación de correo inserte datos de la fuente de datos en esas etiquetas.
    // Si establecemos el indicador "PreserveUnusedTags" en "falso",
    // la combinación de correspondencia convertirá estas etiquetas en MERGEFIELD y las dejará sin completar.
    doc.MailMerge.PreserveUnusedTags = preserveUnusedTags;
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.PreserveUnusedTags.docx");

    // Nuestro documento tiene una etiqueta para una columna llamada "Columna2", que no existe en la tabla.
    // Si establecemos el indicador "PreserveUnusedTags" en "falso", then the mail merge will convert this tag into a MERGEFIELD.
    Assert.AreEqual(doc.GetText().Contains("{{ Column2 }}"), preserveUnusedTags);

    if (preserveUnusedTags)
        Assert.AreEqual(0, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
    else
        Assert.AreEqual(1, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
}

/// <summary>
/// Cree un documento y agregue dos etiquetas de texto sin formato que pueden actuar como MERGEFIELD durante una combinación de correspondencia.
/// </summary>
private static Document CreateSourceDocWithAlternativeMergeFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("{{ Column1 }}");
    builder.Writeln("{{ Column2 }}");

    // Nuestras etiquetas se registrarán como destinos para los datos de combinación de correspondencia solo si establecemos esto en verdadero.
    doc.MailMerge.UseNonMergeFields = true;

    return doc;
}

/// <summary>
/// Crea una tabla de datos simple con una columna.
/// </summary>
private static DataTable CreateSourceTablePreserveUnusedTags()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Rows.Add(new object[] { "Value1" });

    return dataTable;
}
```

### Ver también

* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


