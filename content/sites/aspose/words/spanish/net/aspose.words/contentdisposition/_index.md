---
title: Enum ContentDisposition
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.ContentDisposition enumeración. Enumera diferentes formas de presentar el documento en el navegador del cliente.
type: docs
weight: 330
url: /es/net/aspose.words/contentdisposition/
---
## ContentDisposition enumeration

Enumera diferentes formas de presentar el documento en el navegador del cliente.

```csharp
public enum ContentDisposition
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Attachment | `0` | Envía el documento al navegador y presenta una opción para guardar el documento en el disco o abrirlo en la aplicación asociada con la extensión del documento. |
| Inline | `1` | Envía el documento al navegador y presenta una opción para guardar el documento en el disco o abrirlo dentro del navegador. |

### Observaciones

Tenga en cuenta que el comportamiento real en el navegador del cliente puede verse afectado por la configuración de seguridad del navegador.

### Ejemplos

Muestra cómo realizar una combinación de correspondencia y luego guardar el documento en el navegador del cliente.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD FullName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Company ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Address ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

doc.MailMerge.Execute(new string[] { "FullName", "Company", "Address", "City" },
    new object[] { "James Bond", "MI5 Headquarters", "Milbank", "London" });

// Envía el documento al navegador del cliente.
Assert.That(() => doc.Save(response, "Artifacts/MailMerge.ExecuteArray.docx", ContentDisposition.Inline, null),
    Throws.TypeOf<ArgumentNullException>()); //Lanzado porque HttpResponse es nulo en la prueba.

// Tendremos que cerrar esta respuesta manualmente para asegurarnos de no agregar ningún contenido superfluo al documento después de guardarlo.
Assert.That(() => response.End(), Throws.TypeOf<NullReferenceException>());
```

### Ver también

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


