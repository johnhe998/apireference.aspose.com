---
title: LoadOptions.TempFolder
second_title: Referencia de API de Aspose.Words para .NET
description: LoadOptions propiedad. Permite utilizar archivos temporales al leer un documento. Por defecto esta propiedad esnulo y no se utilizan archivos temporales.
type: docs
weight: 150
url: /es/net/aspose.words.loading/loadoptions/tempfolder/
---
## LoadOptions.TempFolder property

Permite utilizar archivos temporales al leer un documento. Por defecto esta propiedad es`nulo` y no se utilizan archivos temporales.

```csharp
public string TempFolder { get; set; }
```

### Observaciones

La carpeta debe existir y se puede escribir; de lo contrario, se generará una excepción.

Aspose.Words elimina automáticamente todos los archivos temporales cuando finaliza la lectura.

### Ejemplos

Muestra cómo cargar un documento utilizando archivos temporales.

```csharp
// Tenga en cuenta que este enfoque puede reducir el uso de la memoria pero degrada la velocidad
LoadOptions loadOptions = new LoadOptions();
loadOptions.TempFolder = @"C:\TempFolder\";

// Asegurarse de que el directorio existe y cargar
Directory.CreateDirectory(loadOptions.TempFolder);

Document doc = new Document(MyDir + "Document.docx", loadOptions);
```

Muestra cómo utilizar el disco duro en lugar de la memoria al cargar un documento.

```csharp
// Cuando cargamos un documento, varios elementos se almacenan temporalmente en la memoria a medida que se produce la operación de guardar.
// Podemos usar esta opción para usar una carpeta temporal en el sistema de archivos local en su lugar,
// lo que reducirá la sobrecarga de memoria de nuestra aplicación.
LoadOptions options = new LoadOptions();
options.TempFolder = ArtifactsDir + "TempFiles";

// La carpeta temporal especificada debe existir en el sistema de archivos local antes de la operación de carga.
Directory.CreateDirectory(options.TempFolder);

Document doc = new Document(MyDir + "Document.docx", options);

// La carpeta persistirá sin contenido residual de la operación de carga.
Assert.That(Directory.GetFiles(options.TempFolder), Is.Empty);
```

### Ver también

* class [LoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../loadoptions/)
* asamblea [Aspose.Words](../../../)


