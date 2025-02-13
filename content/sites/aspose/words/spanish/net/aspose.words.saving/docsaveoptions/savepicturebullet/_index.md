---
title: DocSaveOptions.SavePictureBullet
second_title: Referencia de API de Aspose.Words para .NET
description: DocSaveOptions propiedad. cuandofalso  los datos de PictureBullet no se guardan en el documento de salida. El valor predeterminado es verdadero .
type: docs
weight: 50
url: /es/net/aspose.words.saving/docsaveoptions/savepicturebullet/
---
## DocSaveOptions.SavePictureBullet property

cuando`falso` , los datos de PictureBullet no se guardan en el documento de salida. El valor predeterminado es **verdadero** .

```csharp
public bool SavePictureBullet { get; set; }
```

### Observaciones

Esta opción se proporciona para Word 97, que no puede funcionar correctamente con datos de PictureBullet. Para eliminar los datos de PictureBullet, establezca la opción en "falso".

### Ejemplos

Muestra cómo omitir los datos de PictureBullet del documento al guardar.

```csharp
Document doc = new Document(MyDir + "Image bullet points.docx");

// Algunos procesadores de texto, como Microsoft Word 97, son incompatibles con los datos de PictureBullet.
// Al establecer una bandera en el objeto SaveOptions,
// podemos convertir todas las viñetas de la imagen en viñetas ordinarias mientras guardamos.
DocSaveOptions saveOptions = new DocSaveOptions(SaveFormat.Doc);
saveOptions.SavePictureBullet = false;

doc.Save(ArtifactsDir + "DocSaveOptions.PictureBullets.doc", saveOptions);
```

### Ver también

* class [DocSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../docsaveoptions/)
* asamblea [Aspose.Words](../../../)


