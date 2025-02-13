---
title: Class WebExtension
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.WebExtensions.WebExtension clase. Representa un objeto de extensión web.
type: docs
weight: 6430
url: /es/net/aspose.words.webextensions/webextension/
---
## WebExtension class

Representa un objeto de extensión web.

```csharp
public class WebExtension
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [AlternateReferences](../../aspose.words.webextensions/webextension/alternatereferences/) { get; } | Especifica referencias alternativas a una extensión web. |
| [Bindings](../../aspose.words.webextensions/webextension/bindings/) { get; } | Especifica una lista de enlaces de extensiones web. |
| [Id](../../aspose.words.webextensions/webextension/id/) { get; set; } | Identifica de forma exclusiva la instancia de la extensión web en el documento actual. |
| [IsFrozen](../../aspose.words.webextensions/webextension/isfrozen/) { get; set; } | Especifica si el usuario puede interactuar con la extensión web o no. |
| [Properties](../../aspose.words.webextensions/webextension/properties/) { get; } | Representa un conjunto de propiedades personalizadas de extensión web. |
| [Reference](../../aspose.words.webextensions/webextension/reference/) { get; } | Especifica la referencia principal a una extensión web. |

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


