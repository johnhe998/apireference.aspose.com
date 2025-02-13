---
title: SaveOptions.ExportGeneratorName
second_title: Referencia de API de Aspose.Words para .NET
description: SaveOptions propiedad. Cuando es verdadero hace que el nombre y la versión de Aspose.Words se incrusten en los archivos producidos. El valor predeterminado es verdadero .
type: docs
weight: 80
url: /es/net/aspose.words.saving/saveoptions/exportgeneratorname/
---
## SaveOptions.ExportGeneratorName property

Cuando es verdadero, hace que el nombre y la versión de Aspose.Words se incrusten en los archivos producidos. El valor predeterminado es **verdadero** .

```csharp
public bool ExportGeneratorName { get; set; }
```

### Ejemplos

Muestra cómo deshabilitar la adición de nombre y versión de Aspose.Words en los archivos producidos.

```csharp
Document doc = new Document();

// Use https://docs.aspose.com/words/net/generator-or-producer-name-included-in-output-documents/ para saber cómo verificar el resultado.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { ExportGeneratorName = false };

doc.Save(ArtifactsDir + "OoxmlSaveOptions.ExportGeneratorName.docx", saveOptions);
```

### Ver también

* class [SaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../saveoptions/)
* asamblea [Aspose.Words](../../../)


