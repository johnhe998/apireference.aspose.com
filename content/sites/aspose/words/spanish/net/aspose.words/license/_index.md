---
title: Class License
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.License clase. Proporciona métodos para licenciar el componente.
type: docs
weight: 3220
url: /es/net/aspose.words/license/
---
## License class

Proporciona métodos para licenciar el componente.

```csharp
public class License
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [License](license/)() | Inicializa una nueva instancia de esta clase. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [SetLicense](../../aspose.words/license/setlicense/#setlicense)(Stream) | Licencia el componente. |
| [SetLicense](../../aspose.words/license/setlicense/#setlicense_1)(string) | Licencia el componente. |

### Ejemplos

Muestra cómo inicializar una licencia para Aspose.Words usando un archivo de licencia en el sistema de archivos local.

```csharp
// Configure la licencia para nuestro producto Aspose.Words pasando el nombre de archivo del sistema de archivos local de un archivo de licencia válido.
string licenseFileName = Path.Combine(LicenseDir, "Aspose.Words.NET.lic");

License license = new License();
license.SetLicense(licenseFileName);

// Crear una copia de nuestro archivo de licencia en la carpeta de binarios de nuestra aplicación.
string licenseCopyFileName = Path.Combine(AssemblyDir, "Aspose.Words.NET.lic");
File.Copy(licenseFileName, licenseCopyFileName);

// Si pasamos el nombre de un archivo sin ruta,
// SetLicense buscará este archivo en varias ubicaciones del sistema de archivos local.
// Una de esas ubicaciones será la carpeta "bin", que contiene una copia de nuestro archivo de licencia.
license.SetLicense("Aspose.Words.NET.lic");
```

### Ver también

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


