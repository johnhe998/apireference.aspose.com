---
title: DocumentBuilder.InsertShape
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentBuilder método. Inserta una forma en línea con el tipo y tamaño especificados.
type: docs
weight: 410
url: /es/net/aspose.words/documentbuilder/insertshape/
---
## InsertShape(ShapeType, double, double) {#insertshape_1}

Inserta una forma en línea con el tipo y tamaño especificados.

```csharp
public Shape InsertShape(ShapeType shapeType, double width, double height)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| shapeType | ShapeType | El tipo de forma que se va a insertar en el documento. |
| width | Double | El ancho de la forma en puntos. |
| height | Double | La altura de la forma en puntos. |

### Valor_devuelto

El nodo de forma que se insertó.

### Ejemplos

Muestra cómo insertar formas DML en un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// A continuación se muestran dos tipos de envoltura que pueden tener las formas.
// 1 - Flotante:
builder.InsertShape(ShapeType.TopCornersRounded, RelativeHorizontalPosition.Page, 100, 
        RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// 2 - En línea:
builder.InsertShape(ShapeType.DiagonalCornersRounded, 50, 50);

// Si necesita crear formas "no primitivas", como SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped,
// TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded o DiagonalCornersRounded,
// luego guarde el documento con cumplimiento "Estricto" o "Transicional", lo que permite guardar la forma como DML.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.Compliance = OoxmlCompliance.Iso29500_2008_Transitional;

doc.Save(ArtifactsDir + "Shape.ShapeInsertion.docx", saveOptions);
```

### Ver también

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ShapeType](../../../aspose.words.drawing/shapetype/)
* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)

---

## InsertShape(ShapeType, RelativeHorizontalPosition, double, RelativeVerticalPosition, double, double, double, WrapType) {#insertshape}

Inserta una forma flotante con la posición, el tamaño y el tipo de ajuste de texto especificados.

```csharp
public Shape InsertShape(ShapeType shapeType, RelativeHorizontalPosition horzPos, double left, 
    RelativeVerticalPosition vertPos, double top, double width, double height, WrapType wrapType)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| shapeType | ShapeType | El tipo de forma para insertar en el documento |
| horzPos | RelativeHorizontalPosition | Especifica desde dónde se mide la distancia horizontal a la forma. |
| left | Double | Distancia en puntos desde el origen hasta el lado izquierdo de la forma. |
| vertPos | RelativeVerticalPosition | Especifica desde dónde se mide la distancia vertical a la forma. |
| top | Double | Distancia en puntos desde el origen hasta el lado superior de la forma. |
| width | Double | El ancho de la forma en puntos. |
| height | Double | El ancho de la forma en puntos. |
| wrapType | WrapType | Especifica cómo ajustar el texto alrededor de la forma. |

### Valor_devuelto

El nodo de forma que se insertó.

### Ejemplos

Muestra cómo insertar formas DML en un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// A continuación se muestran dos tipos de envoltura que pueden tener las formas.
// 1 - Flotante:
builder.InsertShape(ShapeType.TopCornersRounded, RelativeHorizontalPosition.Page, 100, 
        RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// 2 - En línea:
builder.InsertShape(ShapeType.DiagonalCornersRounded, 50, 50);

// Si necesita crear formas "no primitivas", como SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped,
// TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded o DiagonalCornersRounded,
// luego guarde el documento con cumplimiento "Estricto" o "Transicional", lo que permite guardar la forma como DML.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.Compliance = OoxmlCompliance.Iso29500_2008_Transitional;

doc.Save(ArtifactsDir + "Shape.ShapeInsertion.docx", saveOptions);
```

### Ver también

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ShapeType](../../../aspose.words.drawing/shapetype/)
* enum [RelativeHorizontalPosition](../../../aspose.words.drawing/relativehorizontalposition/)
* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* enum [WrapType](../../../aspose.words.drawing/wraptype/)
* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)


