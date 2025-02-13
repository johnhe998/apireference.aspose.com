---
title: Class AsposeWordsPrintDocument
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Rendering.AsposeWordsPrintDocument clase. Proporciona una implementación predeterminada para la impresión de unDocument dentro el framework de impresión .NET.
type: docs
weight: 4280
url: /es/net/aspose.words.rendering/asposewordsprintdocument/
---
## AsposeWordsPrintDocument class

Proporciona una implementación predeterminada para la impresión de un[`Document`](../../aspose.words/document/) dentro el framework de impresión .NET.

```csharp
public class AsposeWordsPrintDocument : PrintDocument
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [AsposeWordsPrintDocument](asposewordsprintdocument/)(Document) | Inicializa una nueva instancia de esta clase. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [CachePrinterSettings](../../aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/)() | Lee y almacena en caché algunos campos dePrinterSettings para reducir el tiempo de impresión. |

### Observaciones

`AsposeWordsPrintDocument` anulaPrintEventArgs) para imprimir el rango de páginas que se especifica enPrinterSettings.

Un solo documento de Word puede constar de varias secciones que especifican páginas con diferentes tamaños, orientación y bandejas de papel.`AsposeWordsPrintDocument` anula QueryPageSettingsEventArgs) para seleccionar correctamente el tamaño del papel, la orientación y el origen del papel al imprimir un documento de Word.

Microsoft Word almacena valores específicos de la impresora para las bandejas de papel en un documento de Word y, por lo tanto, solo imprime en el mismo modelo de impresora que el que se seleccionó cuando el usuario especificó las bandejas de papel dará como resultado la impresión desde las bandejas correctas. Si imprime un documento en una impresora diferente, lo más probable es que se utilice la bandeja de papel predeterminada, no las bandejas especificadas en el documento.

### Ver también

* espacio de nombres [Aspose.Words.Rendering](../../aspose.words.rendering/)
* asamblea [Aspose.Words](../../)


