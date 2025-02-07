---
title: MailMerge.ExecuteADO
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge método. Realiza la combinación de correo desde un objeto Recordset de ADO en el documento.
type: docs
weight: 190
url: /es/net/aspose.words.mailmerging/mailmerge/executeado/
---
## MailMerge.ExecuteADO method

Realiza la combinación de correo desde un objeto Recordset de ADO en el documento.

```csharp
public void ExecuteADO(object recordset)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| recordset | Object | ADO Recordset u objeto Record. |

### Observaciones

Este método es útil cuando pretende usar clases de Aspose.Words como objetos COM de código no administrado, como una aplicación creada usando ASP o Visual Basic 6.0.

Este método ignora laRemoveUnusedRegions opción.

Para obtener más información, consulte la descripción de MailMerge.Execute (DataTable).

### Ejemplos

```csharp
[VBScript]

Dim RS
Set RS = CreateObject("ADODB.Recordset")
RS.Open _
    "SELECT TOP 50 * FROM Customers ORDER BY Country, CompanyName", _
    "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=Northwind.mdb"

Dim License
Set License = CreateObject("Aspose.Words.License")
License.SetLicense "C:\MyPath\MyLicense.lic"

Dim Helper
Set Helper = CreateObject("Aspose.Words.ComHelper")
Dim Doc
Set Doc = Helper.Open("CustomerLabels.doc")

Doc.MailMerge.ExecuteADO RS
Doc.Save "C:\MyPath\CustomerLabels Out VBScript.doc"
```

Muestra cómo ejecutar una combinación de correspondencia con datos de un conjunto de datos ADO.

```csharp
public void ExecuteADO()
{
    Document doc = CreateSourceDocADOMailMerge();

    // Para trabajar con ADO DataSets, necesitaremos agregar una referencia a la biblioteca Microsoft ActiveX Data Objects,
    // que se incluye en la distribución .NET y se almacena en "adodb.dll".
    ADODB.Connection connection = new ADODB.Connection();

    // Crear una cadena de conexión que apunte al archivo de base de datos "Northwind"
    // en nuestro sistema de archivos local y abrir una conexión.
    string connectionString = @"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=" + DatabaseDir + "Northwind.mdb";
    connection.Open(connectionString);

    // Complete nuestro DataSet ejecutando un comando SQL en nuestra base de datos.
    // Los nombres de las columnas en la tabla de resultados deberán corresponder
    // a los valores de los MERGEFIELDS que acomodarán nuestros datos.
    const string command = @"SELECT ProductName, QuantityPerUnit, UnitPrice FROM Products";

    ADODB.Recordset recordset = new ADODB.Recordset();
    recordset.Open(command, connection);

    // Ejecute la combinación de correspondencia y guarde el documento.
    doc.MailMerge.ExecuteADO(recordset);
    doc.Save(ArtifactsDir + "MailMerge.ExecuteADO.docx");
}

/// <summary>
/// Cree un documento en blanco y rellénelo con MERGEFIELDS que aceptarán datos cuando se ejecute una combinación de correspondencia.
/// </summary>
private static Document CreateSourceDocADOMailMerge()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Write("Product:\t");
    builder.InsertField(" MERGEFIELD ProductName");
    builder.Writeln();
    builder.InsertField(" MERGEFIELD QuantityPerUnit");
    builder.Write(" for $");
    builder.InsertField(" MERGEFIELD UnitPrice");

    return doc;
}
```

### Ver también

* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


