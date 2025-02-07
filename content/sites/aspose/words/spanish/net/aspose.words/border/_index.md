---
title: Class Border
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Border clase. Representa un borde de un objeto.
type: docs
weight: 70
url: /es/net/aspose.words/border/
---
## Border class

Representa un borde de un objeto.

```csharp
public class Border : InternableComplexAttr
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Color](../../aspose.words/border/color/) { get; set; } | Obtiene o establece el color del borde. |
| [DistanceFromText](../../aspose.words/border/distancefromtext/) { get; set; } | Obtiene o establece la distancia del borde al texto o al borde de la página en puntos. |
| [IsVisible](../../aspose.words/border/isvisible/) { get; } | Devuelve verdadero si LineStyle no es LineStyle.None. |
| [LineStyle](../../aspose.words/border/linestyle/) { get; set; } | Obtiene o establece el estilo del borde. |
| [LineWidth](../../aspose.words/border/linewidth/) { get; set; } | Obtiene o establece el ancho del borde en puntos. |
| [Shadow](../../aspose.words/border/shadow/) { get; set; } | Obtiene o establece un valor que indica si el borde tiene sombra. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [ClearFormatting](../../aspose.words/border/clearformatting/)() | Restablece las propiedades del borde a los valores predeterminados. |
| [Equals](../../aspose.words/border/equals/#equals)(Border) | Determina si el borde especificado tiene el mismo valor que el borde actual. |
| override [Equals](../../aspose.words/border/equals/#equals_1)(object) | Determina si el objeto especificado tiene el mismo valor que el objeto actual. |
| override [GetHashCode](../../aspose.words/border/gethashcode/)() | Sirve como función hash para este tipo. |

### Observaciones

Los bordes se pueden aplicar a varios elementos del documento, incluido el párrafo, tirada de texto dentro de un párrafo o una celda de tabla.

### Ejemplos

Muestra cómo insertar una cadena rodeada por un borde en un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

Muestra cómo insertar un párrafo con un borde superior.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### Ver también

* class [InternableComplexAttr](../internablecomplexattr/)
* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


