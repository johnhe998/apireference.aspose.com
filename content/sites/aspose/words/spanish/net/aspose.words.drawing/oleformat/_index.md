---
title: Class OleFormat
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.OleFormat clase. Proporciona acceso a los datos de un objeto OLE o control ActiveX.
type: docs
weight: 1020
url: /es/net/aspose.words.drawing/oleformat/
---
## OleFormat class

Proporciona acceso a los datos de un objeto OLE o control ActiveX.

```csharp
public class OleFormat
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [AutoUpdate](../../aspose.words.drawing/oleformat/autoupdate/) { get; set; } | Especifica si el enlace al objeto OLE se actualiza automáticamente o no en Microsoft Word. |
| [Clsid](../../aspose.words.drawing/oleformat/clsid/) { get; } | Obtiene el CLSID del objeto OLE. |
| [IconCaption](../../aspose.words.drawing/oleformat/iconcaption/) { get; } | Obtiene el título del icono del objeto OLE. |
| [IsLink](../../aspose.words.drawing/oleformat/islink/) { get; } | Devuelve verdadero si el objeto OLE está vinculado (cuando[`SourceFullName`](./sourcefullname/) se especifica). |
| [IsLocked](../../aspose.words.drawing/oleformat/islocked/) { get; set; } | Especifica si el enlace al objeto OLE está bloqueado para actualizaciones. |
| [OleControl](../../aspose.words.drawing/oleformat/olecontrol/) { get; } | Obtiene[`OleControl`](./olecontrol/) objetos si este objeto OLE es un control ActiveX. De lo contrario, esta propiedad es nula. |
| [OleIcon](../../aspose.words.drawing/oleformat/oleicon/) { get; } | Obtiene el aspecto de dibujo del objeto OLE. Cuando **verdadero** , el objeto OLE se muestra como un icono. cuando **falso** , el objeto OLE se muestra como content. |
| [OlePackage](../../aspose.words.drawing/oleformat/olepackage/) { get; } | Proporcionar acceso a[`OlePackage`](../olepackage/) si el objeto OLE es un paquete OLE. Devuelve nulo en caso contrario. |
| [ProgId](../../aspose.words.drawing/oleformat/progid/) { get; set; } | Obtiene o establece el ProgID del objeto OLE. |
| [SourceFullName](../../aspose.words.drawing/oleformat/sourcefullname/) { get; set; } | Obtiene o establece la ruta y el nombre del archivo de origen del objeto OLE vinculado. |
| [SourceItem](../../aspose.words.drawing/oleformat/sourceitem/) { get; set; } | Obtiene o establece una cadena que se utiliza para identificar la parte del archivo de origen que se vincula. |
| [SuggestedExtension](../../aspose.words.drawing/oleformat/suggestedextension/) { get; } | Obtiene la extensión de archivo sugerida para el objeto incrustado actual si desea guardarlo en un archivo. |
| [SuggestedFileName](../../aspose.words.drawing/oleformat/suggestedfilename/) { get; } | Obtiene el nombre de archivo sugerido para el objeto incrustado actual si desea guardarlo en un archivo. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetOleEntry](../../aspose.words.drawing/oleformat/getoleentry/)(string) | Obtiene la entrada de datos del objeto OLE. |
| [GetRawData](../../aspose.words.drawing/oleformat/getrawdata/)() | Obtiene datos sin procesar del objeto OLE. |
| [Save](../../aspose.words.drawing/oleformat/save/#save)(Stream) | Guarda los datos del objeto incrustado en el flujo especificado. |
| [Save](../../aspose.words.drawing/oleformat/save/#save_1)(string) | Guarda los datos del objeto incrustado en un archivo con el nombre especificado. |

### Observaciones

Utilizar el[`OleFormat`](../shape/oleformat/) propiedad para acceder a los datos de un objeto OLE. No crea instancias de la`OleFormat` clase directamente.

### Ejemplos

Muestra cómo extraer objetos OLE incrustados en archivos.

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// El objeto OLE de la primera forma es una hoja de cálculo de Microsoft Excel.
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// Nuestro objeto no se actualiza automáticamente ni está bloqueado para actualizaciones.
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// Si planeamos guardar el objeto OLE en un archivo en el sistema de archivos local,
// podemos usar la propiedad "SuggestedExtension" para determinar qué extensión de archivo aplicar al archivo.
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// A continuación se muestran dos formas de guardar un objeto OLE en un archivo en el sistema de archivos local.
// 1 - Guárdelo a través de una transmisión:
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - Guardarlo directamente en un nombre de archivo:
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### Ver también

* espacio de nombres [Aspose.Words.Drawing](../../aspose.words.drawing/)
* asamblea [Aspose.Words](../../)


