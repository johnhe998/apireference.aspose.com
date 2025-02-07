---
title: ShapeBase.HRef
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Obtiene o establece la dirección de hipervínculo completa para una forma.
type: docs
weight: 220
url: /es/net/aspose.words.drawing/shapebase/href/
---
## ShapeBase.HRef property

Obtiene o establece la dirección de hipervínculo completa para una forma.

```csharp
public string HRef { get; set; }
```

### Observaciones

El valor predeterminado es una cadena vacía.

continuación se muestran ejemplos de valores válidos para esta propiedad:

URI completo:`https://www.aspose.com/`.

Nombre completo del archivo:`C:\\Mis documentos\\SalesReport.doc`.

URI relativo:`../../../recurso.txt`

Nombre de archivo relativo:`..\\Mis Documentos\\InformeVentas.doc`.

Marcador dentro de otro documento:`https://www.aspose.com/Products/Default.aspx#Suites`

Marcar dentro de este documento:`#BookmakNombre`.

### Ejemplos

Muestra cómo insertar una forma que contiene una imagen y también es un hipervínculo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.HRef = "https://foro.aspose.com/";
shape.Target = "New Window";
shape.ScreenTip = "Aspose.Words Support Forums";

// Ctrl + clic izquierdo en la forma en Microsoft Word abrirá una nueva ventana del navegador web
// y nos lleva al hipervínculo en la propiedad "HRef".
doc.Save(ArtifactsDir + "Image.InsertImageWithHyperlink.docx");
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


