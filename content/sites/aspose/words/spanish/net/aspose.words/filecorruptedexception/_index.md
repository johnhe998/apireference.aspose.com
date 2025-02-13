---
title: Class FileCorruptedException
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.FileCorruptedException clase. Lanzado durante la carga del documento cuando el documento parece estar dañado e imposible de cargar.
type: docs
weight: 2620
url: /es/net/aspose.words/filecorruptedexception/
---
## FileCorruptedException class

Lanzado durante la carga del documento, cuando el documento parece estar dañado e imposible de cargar.

```csharp
public class FileCorruptedException : Exception
```

### Ejemplos

Muestra cómo capturar una FileCorruptedException.

```csharp
try
{
    // Si recibimos un mensaje de error de "Contenido ilegible" al intentar abrir un documento usando Microsoft Word,
    // lo más probable es que obtengamos una excepción al intentar cargar ese documento usando Aspose.Words.
    Document doc = new Document(MyDir + "Corrupted document.docx");
}
catch (FileCorruptedException e)
{
    Console.WriteLine(e.Message);
}
```

### Ver también

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


