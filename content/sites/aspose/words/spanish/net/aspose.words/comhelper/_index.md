---
title: Class ComHelper
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.ComHelper clase. Proporciona métodos para que los clientes COM carguen un documento en Aspose.Words.
type: docs
weight: 210
url: /es/net/aspose.words/comhelper/
---
## ComHelper class

Proporciona métodos para que los clientes COM carguen un documento en Aspose.Words.

```csharp
public class ComHelper
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [ComHelper](comhelper/)() | Inicializa una nueva instancia de esta clase. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [Open](../../aspose.words/comhelper/open/#open)(Stream) | Permite cargar una aplicación COM[`Document`](../document/) de un arroyo. |
| [Open](../../aspose.words/comhelper/open/#open_1)(string) | Permite que una aplicación COM cargue un[`Document`](../document/) de un archivo. |
| [OpenIStream](../../aspose.words/comhelper/openistream/)(IStream) | Permite que una aplicación COM cargue un[`Document`](../document/) de un objeto IStream. |

### Observaciones

Utilizar el`ComHelper` clase para cargar un documento desde un archivo o flujo en un [`Document`](../document/) objeto en una aplicación COM.

los[`Document`](../document/)class proporciona un constructor predeterminado para crear un nuevo documento y también proporciona constructores sobrecargados para cargar un documento desde un archivo o flujo. Si está usando Aspose.Words desde una aplicación .NET, puede usar todos los[`Document`](../document/) constructores directamente, pero si está utilizando Aspose.Words desde una aplicación COM, solo el valor predeterminado[`Document`](../document/) El constructor está disponible.

### Ejemplos

```csharp
[VBScript]

Dim helper
Set helper = CreateObject("Aspose.Words.ComHelper")

Dim doc
Set doc = helper.Open(fileName)
```

Muestra cómo abrir documentos utilizando la clase ComHelper.

```csharp
// La clase ComHelper nos permite cargar documentos desde clientes COM.
ComHelper comHelper = new ComHelper();

// 1 - Usando un nombre de archivo del sistema local:
Document doc = comHelper.Open(MyDir + "Document.docx");

Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());

// 2 - De un flujo:
using (FileStream stream = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    doc = comHelper.Open(stream);

    Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());
}
```

### Ver también

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


