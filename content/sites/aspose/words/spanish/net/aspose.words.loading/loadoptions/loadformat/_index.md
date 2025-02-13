---
title: LoadOptions.LoadFormat
second_title: Referencia de API de Aspose.Words para .NET
description: LoadOptions propiedad. Especifica el formato del documento que se cargará. El valor predeterminado esAuto .
type: docs
weight: 90
url: /es/net/aspose.words.loading/loadoptions/loadformat/
---
## LoadOptions.LoadFormat property

Especifica el formato del documento que se cargará. El valor predeterminado esAuto .

```csharp
public LoadFormat LoadFormat { get; set; }
```

### Observaciones

Se recomienda especificar elAutovalor y dejar que Aspose.Words detecte el formato de archivo automáticamente. Si conoce el formato del documento que está a punto de cargar, puede especificar el formato explícitamente y esto reducirá ligeramente el tiempo de carga por la sobrecarga asociada con la detección automática del formato. Si especifica un formato de carga explícito y cambiará fuera incorrecto, se invocará la detección automática y se realizará un segundo intento de cargar el archivo.

### Ejemplos

Muestra cómo especificar un URI base al abrir un documento html.

```csharp
// Supongamos que queremos cargar un documento .html que contiene una imagen enlazada por una URI relativa
// mientras la imagen está en una ubicación diferente. En ese caso, necesitaremos convertir el URI relativo en uno absoluto.
  // Podemos proporcionar un URI base usando un objeto HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// Si bien la imagen se rompió en el .html de entrada, nuestro URI base personalizado nos ayudó a reparar el enlace.
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// Este documento de salida mostrará la imagen que faltaba.
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

### Ver también

* enum [LoadFormat](../../../aspose.words/loadformat/)
* class [LoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../loadoptions/)
* asamblea [Aspose.Words](../../../)


