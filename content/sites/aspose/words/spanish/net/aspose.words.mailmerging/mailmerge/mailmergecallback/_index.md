---
title: MailMerge.MailMergeCallback
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge propiedad. Permite manejar eventos particulares durante la combinación de correspondencia.
type: docs
weight: 40
url: /es/net/aspose.words.mailmerging/mailmerge/mailmergecallback/
---
## MailMerge.MailMergeCallback property

Permite manejar eventos particulares durante la combinación de correspondencia.

```csharp
public IMailMergeCallback MailMergeCallback { get; set; }
```

### Ejemplos

Muestra cómo definir una lógica personalizada para manejar eventos durante la combinación de correspondencia.

```csharp
public void Callback()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Insertar dos etiquetas de combinación de correspondencia que hagan referencia a dos columnas en una fuente de datos.
    builder.Write("{{FirstName}}");
    builder.Write("{{LastName}}");

    // Cree una fuente de datos que solo contenga una de las columnas a las que hacen referencia nuestras etiquetas de fusión.
    DataTable table = new DataTable("Test");
    table.Columns.Add("FirstName");
    table.Rows.Add("John");
    table.Rows.Add("Jane");

    // Configure nuestra combinación de correspondencia para usar etiquetas de combinación de correspondencia alternativas.
    doc.MailMerge.UseNonMergeFields = true;

    // Luego, asegúrese de que la combinación de correspondencia convierta etiquetas, como nuestra etiqueta "Apellido",
    // en MERGEFIELDs en los documentos combinados.
    doc.MailMerge.PreserveUnusedTags = false;

    MailMergeTagReplacementCounter counter = new MailMergeTagReplacementCounter();
    doc.MailMerge.MailMergeCallback = counter;
    doc.MailMerge.Execute(table);

    Assert.AreEqual(1, counter.TagsReplacedCount);
}

/// <summary>
/// Cuenta el número de veces que una combinación de correspondencia reemplaza etiquetas de combinación de correspondencia que no pudo llenar con datos con MERGEFIELDs.
/// </summary>
private class MailMergeTagReplacementCounter : IMailMergeCallback
{
    public void TagsReplaced()
    {
        TagsReplacedCount++;
    }

    public int TagsReplacedCount { get; private set; }
}
```

### Ver también

* interface [IMailMergeCallback](../../imailmergecallback/)
* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


