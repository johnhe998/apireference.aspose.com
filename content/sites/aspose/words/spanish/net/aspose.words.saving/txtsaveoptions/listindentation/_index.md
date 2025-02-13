---
title: TxtSaveOptions.ListIndentation
second_title: Referencia de API de Aspose.Words para .NET
description: TxtSaveOptions propiedad. Obtiene un objeto ListIndentation que especifica cuántos y qué caracteres usar para la sangría de los niveles de la lista. De forma predeterminada el recuento de caracteres 0 es cero lo que significa que no hay sangría.
type: docs
weight: 30
url: /es/net/aspose.words.saving/txtsaveoptions/listindentation/
---
## TxtSaveOptions.ListIndentation property

Obtiene un objeto ListIndentation que especifica cuántos y qué caracteres usar para la sangría de los niveles de la lista. De forma predeterminada, el recuento de caracteres '\0' es cero, lo que significa que no hay sangría.

```csharp
public TxtListIndentation ListIndentation { get; }
```

### Ejemplos

Muestra cómo configurar la sangría de la lista al guardar un documento en texto sin formato.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea una lista con tres niveles de sangría.
builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent(); 
builder.Write("Item 3");

// Crear un objeto "TxtSaveOptions", que podemos pasar al método "Guardar" del documento
// para modificar cómo guardamos el documento en texto sin formato.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// Establecer la propiedad "Carácter" para asignar un carácter para usar
// para el relleno que simula la sangría de la lista en texto sin formato.
txtSaveOptions.ListIndentation.Character = ' ';

// Establecer la propiedad "Contar" para especificar el número de veces
// para colocar el carácter de relleno para cada nivel de sangría de la lista.
txtSaveOptions.ListIndentation.Count = 3;

doc.Save(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt");

Assert.AreEqual("1. Item 1\r\n" +
                "   a. Item 2\r\n" +
                "      i. Item 3\r\n", docText);
```

### Ver también

* class [TxtListIndentation](../../txtlistindentation/)
* class [TxtSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../txtsaveoptions/)
* asamblea [Aspose.Words](../../../)


