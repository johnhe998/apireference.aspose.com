---
title: MailMergeSettings.MailAsAttachment
second_title: Referencia de API de Aspose.Words para .NET
description: MailMergeSettings propiedad. Especifica que los documentos producidos durante una operación de combinación de correo deben enviarse por correo electrónico como datos adjuntos en lugar de que el cuerpo del correo electrónico real. El valor predeterminado esfalso .
type: docs
weight: 120
url: /es/net/aspose.words.settings/mailmergesettings/mailasattachment/
---
## MailMergeSettings.MailAsAttachment property

Especifica que los documentos producidos durante una operación de combinación de correo deben enviarse por correo electrónico como datos adjuntos en lugar de que el cuerpo del correo electrónico real. El valor predeterminado es`falso` .

```csharp
public bool MailAsAttachment { get; set; }
```

### Ejemplos

Muestra cómo ejecutar una combinación de correspondencia mientras se conecta a una fuente de datos externa.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");
MailMergeSettings settings = doc.MailMergeSettings;

Console.WriteLine($"Connection string:\n\t{settings.ConnectString}");
Console.WriteLine($"Mail merge docs as attachment:\n\t{settings.MailAsAttachment}");
Console.WriteLine($"Mail merge doc e-mail subject:\n\t{settings.MailSubject}");
Console.WriteLine($"Column that contains e-mail addresses:\n\t{settings.AddressFieldName}");
Console.WriteLine($"Active record:\n\t{settings.ActiveRecord}");

Odso odso = settings.Odso;

Console.WriteLine($"File will connect to data source located in:\n\t\"{odso.DataSource}\"");
Console.WriteLine($"Source type:\n\t{odso.DataSourceType}");
Console.WriteLine($"UDL connection string:\n\t{odso.UdlConnectString}");
Console.WriteLine($"Table:\n\t{odso.TableName}");
Console.WriteLine($"Query:\n\t{doc.MailMergeSettings.Query}");

// Podemos restablecer estas configuraciones borrándolas. Una vez que hagamos eso y guardemos el documento,
// Microsoft Word ya no ejecutará una combinación de correo cuando lo usemos para cargar el documento.
settings.Clear();

doc.Save(ArtifactsDir + "MailMerge.OdsoEmail.docx");
```

### Ver también

* class [MailMergeSettings](../)
* espacio de nombres [Aspose.Words.Settings](../../mailmergesettings/)
* asamblea [Aspose.Words](../../../)


