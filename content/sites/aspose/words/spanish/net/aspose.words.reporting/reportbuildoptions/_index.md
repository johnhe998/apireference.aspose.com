---
title: Enum ReportBuildOptions
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Reporting.ReportBuildOptions enumeración. Especifica opciones que controlan el comportamiento deReportingEngine al crear un informe.
type: docs
weight: 4460
url: /es/net/aspose.words.reporting/reportbuildoptions/
---
## ReportBuildOptions enumeration

Especifica opciones que controlan el comportamiento de[`ReportingEngine`](../reportingengine/) al crear un informe.

```csharp
[Flags]
public enum ReportBuildOptions
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| None | `0` | Especifica las opciones predeterminadas. |
| AllowMissingMembers | `1` | Especifica que el motor debe tratar los miembros de objetos faltantes como literales nulos. Esta opción solo afecta el acceso a miembros de objetos de instancia (es decir, no estáticos) y métodos de extensión. Si esta opción no está configurada, el motor genera una excepción cuando encuentra un miembro de objeto faltante. |
| RemoveEmptyParagraphs | `2` | Especifica que el motor debe eliminar los párrafos que quedan vacíos después de que las etiquetas de sintaxis de plantilla se eliminen o reemplacen con valores vacíos. |
| InlineErrorMessages | `4` | Especifica que el motor debe incluir mensajes de error de sintaxis de plantilla en línea en los documentos de salida. Si esta opción no está configurada, el motor lanza una excepción cuando encuentra un error de sintaxis. |
| UseLegacyHeaderFooterVisiting | `8` | Especifica que el motor debe visitar los nodos secundarios de la sección (encabezados, pies de página, cuerpos) en un orden compatible con las versiones de Aspose.Words anteriores a la 21.9. |
| RespectJpegExifOrientation | `10` | Especifica que el motor debe usar valores de orientación de imagen EXIF ​​para rotar adecuadamente las imágenes JPEG insertadas . |

### Ver también

* espacio de nombres [Aspose.Words.Reporting](../../aspose.words.reporting/)
* asamblea [Aspose.Words](../../)


