---
title: Document.RemoveMacros
second_title: Referencia de API de Aspose.Words para .NET
description: Document método. Elimina todas las macros el proyecto VBA así como las barras de herramientas y las personalizaciones de comandos del documento.
type: docs
weight: 650
url: /es/net/aspose.words/document/removemacros/
---
## Document.RemoveMacros method

Elimina todas las macros (el proyecto VBA), así como las barras de herramientas y las personalizaciones de comandos del documento.

```csharp
public void RemoveMacros()
```

### Observaciones

Al eliminar todas las macros de un documento, puede asegurarse de que el documento no contenga virus de macro.

### Ejemplos

Muestra cómo eliminar todas las macros de un documento.

```csharp
Document doc = new Document(MyDir + "Macro.docm");

Assert.IsTrue(doc.HasMacros);
Assert.AreEqual("Project", doc.VbaProject.Name);

// Elimina el proyecto VBA del documento, junto con todas sus macros.
doc.RemoveMacros();

Assert.IsFalse(doc.HasMacros);
Assert.Null(doc.VbaProject);
```

### Ver también

* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


