---
title: CellFormat.SetPaddings
second_title: Referencia de API de Aspose.Words para .NET
description: CellFormat método. Establece la cantidad de espacio en puntos para agregar a la izquierda/arriba/derecha/abajo del contenido de la celda.
type: docs
weight: 160
url: /es/net/aspose.words.tables/cellformat/setpaddings/
---
## CellFormat.SetPaddings method

Establece la cantidad de espacio (en puntos) para agregar a la izquierda/arriba/derecha/abajo del contenido de la celda.

```csharp
public void SetPaddings(double leftPadding, double topPadding, double rightPadding, 
    double bottomPadding)
```

### Ejemplos

Muestra cómo rellenar el contenido de una celda con espacios en blanco.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Establecer una distancia de relleno (en puntos) entre el borde y el contenido del texto
// de cada celda de la tabla que creamos con el generador de documentos. 
builder.CellFormat.SetPaddings(5, 10, 40, 50);

// Cree una tabla con una celda cuyo contenido tendrá relleno de espacios en blanco.
builder.StartTable();
builder.InsertCell();
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
              "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

doc.Save(ArtifactsDir + "CellFormat.Padding.docx");
```

### Ver también

* class [CellFormat](../)
* espacio de nombres [Aspose.Words.Tables](../../cellformat/)
* asamblea [Aspose.Words](../../../)


