---
title: BorderCollection.Item
second_title: Referencia de API de Aspose.Words para .NET
description: BorderCollection propiedad. Recupera un objeto Borde por tipo de borde.
type: docs
weight: 60
url: /es/net/aspose.words/bordercollection/item/
---
## BorderCollection indexer (1 of 2)

Recupera un objeto Borde por tipo de borde.

```csharp
public Border this[BorderType borderType] { get; }
```

| Parámetro | Descripción |
| --- | --- |
| borderType | A[`BorderType`](../../bordertype/) value que especifica el tipo de borde a recuperar. |

### Observaciones

Tenga en cuenta que no todos los bordes están presentes para los diferentes elementos del documento. Este método genera una excepción si solicita un borde que no se aplica al objeto actual.

### Ejemplos

Muestra cómo decorar texto con bordes y sombreado.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;

Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = Color.LightCoral;
shading.ForegroundPatternColor = Color.LightSalmon;

builder.Write("This paragraph is formatted with a double border and shading.");
doc.Save(ArtifactsDir + "DocumentBuilder.ApplyBordersAndShading.docx");
```

### Ver también

* class [Border](../../border/)
* enum [BorderType](../../bordertype/)
* class [BorderCollection](../)
* espacio de nombres [Aspose.Words](../../bordercollection/)
* asamblea [Aspose.Words](../../../)

---

## BorderCollection indexer (2 of 2)

Recupera un objeto Border por index.

```csharp
public Border this[int index] { get; }
```

| Parámetro | Descripción |
| --- | --- |
| index | Índice de base cero del borde que se va a recuperar. |

### Ejemplos

Muestra cómo las colecciones de borde pueden compartir elementos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Write("Paragraph 2.");

// Dado que usamos la misma configuración de borde al crear
// estos párrafos, sus colecciones de bordes comparten los mismos elementos.
BorderCollection firstParagraphBorders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;
BorderCollection secondParagraphBorders = builder.CurrentParagraph.ParagraphFormat.Borders;

for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsTrue(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());
    Assert.False(firstParagraphBorders[i].IsVisible);
}

foreach (Border border in secondParagraphBorders)
    border.LineStyle = LineStyle.DotDash;

// Después de cambiar el estilo de línea de los bordes solo en el segundo párrafo,
// las colecciones fronterizas ya no comparten los mismos elementos.
for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsFalse(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreNotEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());

    // Cambiar la apariencia de un borde vacío lo hace visible.
    Assert.True(secondParagraphBorders[i].IsVisible);
}

doc.Save(ArtifactsDir + "Border.SharedElements.docx");
```

### Ver también

* class [Border](../../border/)
* class [BorderCollection](../)
* espacio de nombres [Aspose.Words](../../bordercollection/)
* asamblea [Aspose.Words](../../../)


