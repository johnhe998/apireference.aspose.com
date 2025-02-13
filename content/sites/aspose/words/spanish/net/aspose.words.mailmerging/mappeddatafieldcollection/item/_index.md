---
title: MappedDataFieldCollection.Item
second_title: Referencia de API de Aspose.Words para .NET
description: MappedDataFieldCollection propiedad. Obtiene o establece el nombre del campo en el origen de datos asociado con el campo de combinación de correspondencia especificado.
type: docs
weight: 20
url: /es/net/aspose.words.mailmerging/mappeddatafieldcollection/item/
---
## MappedDataFieldCollection indexer

Obtiene o establece el nombre del campo en el origen de datos asociado con el campo de combinación de correspondencia especificado.

```csharp
public string this[string documentFieldName] { get; set; }
```

### Ejemplos

Muestra cómo asignar columnas de datos y MERGEFIELD con diferentes nombres para que los datos se transfieran entre ellos durante una combinación de correspondencia.

```csharp
public void MappedDataFieldCollection()
{
    Document doc = CreateSourceDocMappedDataFields();
    DataTable dataTable = CreateSourceTableMappedDataFields();

    // La tabla tiene una columna llamada "Columna2", pero no hay MERGEFIELD con ese nombre.
    // Además, tenemos un MERGEFIELD llamado "Columna3", pero la fuente de datos no tiene una columna con ese nombre.
    // Si los datos de "Columna2" son adecuados para el MERGEFIELD "Columna3",
    // podemos asignar ese nombre de columna al MERGEFIELD en el par clave/valor "MappedDataFields".
    MappedDataFieldCollection mappedDataFields = doc.MailMerge.MappedDataFields;

    // Podemos vincular un nombre de columna de fuente de datos a un nombre MERGEFIELD como este.
    mappedDataFields.Add("MergeFieldName", "DataSourceColumnName");

    // Vincule la columna de la fuente de datos denominada "Columna2" a los MERGEFIELD denominados "Columna3".
    mappedDataFields.Add("Column3", "Column2");

    // El nombre MERGEFIELD es la "clave" para el nombre "valor" de la columna de la fuente de datos respectiva.
    Assert.AreEqual("DataSourceColumnName", mappedDataFields["MergeFieldName"]);
    Assert.True(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.True(mappedDataFields.ContainsValue("DataSourceColumnName"));

    // Ahora, si ejecutamos esta combinación de correo, los MERGEFIELD "Column3" tomarán datos de "Column2" de la tabla.
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.MappedDataFieldCollection.docx");

    // Podemos iterar sobre los elementos de esta colección.
    Assert.AreEqual(2, mappedDataFields.Count);

    using (IEnumerator<KeyValuePair<string, string>> enumerator = mappedDataFields.GetEnumerator())
        while (enumerator.MoveNext())
            Console.WriteLine(
                $"Column named {enumerator.Current.Value} is mapped to MERGEFIELDs named {enumerator.Current.Key}");

    // También podemos eliminar elementos de la colección.
    mappedDataFields.Remove("MergeFieldName");

    Assert.False(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.False(mappedDataFields.ContainsValue("DataSourceColumnName"));

    mappedDataFields.Clear();

    Assert.AreEqual(0, mappedDataFields.Count);
}

/// <summary>
/// Crea un documento con 2 MERGEFIELDs, uno de los cuales no tiene un
/// columna correspondiente en la tabla de datos del método a continuación.
/// </summary>
private static Document CreateSourceDocMappedDataFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column3");

    return doc;
}

/// <summary>
/// Crear una tabla de datos con 2 columnas, una de las cuales no tiene
/// MERGEFIELD correspondiente en el documento fuente del método anterior.
/// </summary>
private static DataTable CreateSourceTableMappedDataFields()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value1", "Value2" });

    return dataTable;
}
```

### Ver también

* class [MappedDataFieldCollection](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mappeddatafieldcollection/)
* asamblea [Aspose.Words](../../../)


