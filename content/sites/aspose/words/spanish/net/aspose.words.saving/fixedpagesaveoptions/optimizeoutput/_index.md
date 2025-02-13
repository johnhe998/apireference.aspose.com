---
title: FixedPageSaveOptions.OptimizeOutput
second_title: Referencia de API de Aspose.Words para .NET
description: FixedPageSaveOptions propiedad. El indicador indica si es necesario optimizar la salida. Si este indicador se establece se eliminan los lienzos anidados redundantes y los lienzos vacíos también se concatenan los glifos vecinos con el mismo formato. Nota La precisión de la visualización del contenido puede verse afectada si esta propiedad se establece en verdadero. El valor predeterminado es falso.
type: docs
weight: 50
url: /es/net/aspose.words.saving/fixedpagesaveoptions/optimizeoutput/
---
## FixedPageSaveOptions.OptimizeOutput property

El indicador indica si es necesario optimizar la salida. Si este indicador se establece, se eliminan los lienzos anidados redundantes y los lienzos vacíos, también se concatenan los glifos vecinos con el mismo formato. Nota: La precisión de la visualización del contenido puede verse afectada si esta propiedad se establece en verdadero. El valor predeterminado es falso.

```csharp
public virtual bool OptimizeOutput { get; set; }
```

### Ejemplos

Muestra cómo optimizar los objetos del documento mientras se guardan en xps.

```csharp
Document doc = new Document(MyDir + "Unoptimized document.docx");

// Crear un objeto "XpsSaveOptions" para pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .XPS.
XpsSaveOptions saveOptions = new XpsSaveOptions();

// Establezca la propiedad "OptimizeOutput" en "true" para tomar medidas como eliminar lienzos anidados o vacíos
// y concatenar ejecuciones adyacentes con formato idéntico para optimizar el contenido del documento de salida.
// Esto puede afectar la apariencia del documento.
// Establezca la propiedad "OptimizeOutput" en "falso" para guardar el documento normalmente.
saveOptions.OptimizeOutput = optimizeOutput;

doc.Save(ArtifactsDir + "XpsSaveOptions.OptimizeOutput.xps", saveOptions);
```

### Ver también

* class [FixedPageSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* asamblea [Aspose.Words](../../../)


