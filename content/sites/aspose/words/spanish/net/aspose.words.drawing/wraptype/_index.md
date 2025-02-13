---
title: Enum WrapType
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.WrapType enumeración. Especifica cómo se envuelve el texto alrededor de una forma o imagen.
type: docs
weight: 1250
url: /es/net/aspose.words.drawing/wraptype/
---
## WrapType enumeration

Especifica cómo se envuelve el texto alrededor de una forma o imagen.

```csharp
public enum WrapType
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| None | `3` | No hay texto que envuelva la forma. La forma se coloca detrás o delante del texto. |
| Inline | `0` | La forma permanece en la misma capa que el texto y se trata como un carácter. |
| TopBottom | `1` | El texto se detiene en la parte superior de la forma y se reinicia en la línea debajo de la forma. |
| Square | `2` | Envuelve el texto alrededor de todos los lados del cuadro delimitador cuadrado de la forma. |
| Tight | `4` | Envuelve firmemente los bordes de la forma, en lugar de envolver alrededor del cuadro delimitador. |
| Through | `5` | Igual que Tight, pero envuelve cualquier parte de la forma que esté abierta. |

### Ejemplos

Muestra cómo insertar una imagen flotante en el centro de una página.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta una imagen flotante que aparecerá detrás del texto superpuesto y alinéala con el centro de la página.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

Muestra cómo insertar una imagen y usarla como marca de agua.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta la imagen en el encabezado para que sea visible en todas las páginas.
Image image = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
Shape shape = builder.InsertImage(image);
shape.WrapType = WrapType.None;
shape.BehindText = true;

// Coloca la imagen en el centro de la página.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermark.docx");
```

Muestra cómo insertar una imagen y usarla como marca de agua (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta la imagen en el encabezado para que sea visible en todas las páginas.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

using (SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png"))
{
    builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
    Shape shape = builder.InsertImage(image);
    shape.WrapType = WrapType.None;
    shape.BehindText = true;

    // Coloca la imagen en el centro de la página.
    shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
    shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
    shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
    shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;
}

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermarkNetStandard2.docx");
```

### Ver también

* property [WrapType](../shapebase/wraptype/)
* espacio de nombres [Aspose.Words.Drawing](../../aspose.words.drawing/)
* asamblea [Aspose.Words](../../)


