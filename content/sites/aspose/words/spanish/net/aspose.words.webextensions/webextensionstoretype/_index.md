---
title: Enum WebExtensionStoreType
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.WebExtensions.WebExtensionStoreType enumeración. Enumera los tipos disponibles de una tienda de extensiones web.
type: docs
weight: 6510
url: /es/net/aspose.words.webextensions/webextensionstoretype/
---
## WebExtensionStoreType enumeration

Enumera los tipos disponibles de una tienda de extensiones web.

```csharp
public enum WebExtensionStoreType
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| SPCatalog | `0` | Especifica que el tipo de tienda es catálogo corporativo de SharePoint. |
| OMEX | `1` | Especifica que el tipo de tienda es Office.com. |
| SPApp | `2` | Especifica que el tipo de tienda es una aplicación web de SharePoint. |
| Exchange | `3` | Especifica que el tipo de tienda es un servidor de Exchange. |
| FileSystem | `4` | Especifica que el tipo de almacenamiento es un recurso compartido del sistema de archivos. |
| Registry | `5` | Especifica que el tipo de almacenamiento es el registro del sistema. |
| ExCatalog | `6` | Especifica que el tipo de tienda es Implementación centralizada a través de Exchange. |
| Default | `0` | Valor por defecto. |

### Ejemplos

Muestra cómo agregar una extensión web a un documento.

```csharp
Document doc = new Document();

// Crear un panel de tareas con el complemento "MyScript", que será utilizado por el documento,
// luego establezca su ubicación predeterminada.
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// Si hay varios paneles de tareas en la misma ubicación de acoplamiento, podemos establecer este índice para organizarlos.
myScriptTaskPane.Row = 1;

// Cree un complemento llamado "MyScript Math Sample", dentro del cual se mostrará el panel de tareas.
WebExtension webExtension = myScriptTaskPane.WebExtension;

// Establecer parámetros de referencia del almacén de aplicaciones para nuestro complemento, como el ID.
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// Permitir que el usuario interactúe con el complemento.
webExtension.IsFrozen = false;

// Podemos acceder a la extensión web en Microsoft Word a través de Desarrollador -> Complementos.
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// Eliminar todos los paneles de tareas de la extensión web a la vez de esta manera.
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Ver también

* espacio de nombres [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* asamblea [Aspose.Words](../../)


