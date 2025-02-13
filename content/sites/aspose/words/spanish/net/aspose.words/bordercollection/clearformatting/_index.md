---
title: BorderCollection.ClearFormatting
second_title: Referencia de API de Aspose.Words para .NET
description: BorderCollection método. Elimina todos los bordes de un objeto.
type: docs
weight: 140
url: /es/net/aspose.words/bordercollection/clearformatting/
---
## BorderCollection.ClearFormatting method

Elimina todos los bordes de un objeto.

```csharp
public void ClearFormatting()
```

### Ejemplos

Muestra cómo eliminar todos los bordes de todos los párrafos de un documento.

```csharp
Document doc = new Document(MyDir + "Borders.docx");

// El primer párrafo de este documento tiene bordes visibles con esta configuración.
BorderCollection firstParagraphBorders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;

Assert.AreEqual(Color.Red.ToArgb(), firstParagraphBorders.Color.ToArgb());
Assert.AreEqual(LineStyle.Single, firstParagraphBorders.LineStyle);
Assert.AreEqual(3.0d, firstParagraphBorders.LineWidth);

// Use el método "ClearFormatting" en cada párrafo para eliminar todos los bordes.
foreach (Paragraph paragraph in doc.FirstSection.Body.Paragraphs)
{
    paragraph.ParagraphFormat.Borders.ClearFormatting();

    foreach (Border border in paragraph.ParagraphFormat.Borders)
    {
        Assert.AreEqual(Color.Empty.ToArgb(), border.Color.ToArgb());
        Assert.AreEqual(LineStyle.None, border.LineStyle);
        Assert.AreEqual(0.0d, border.LineWidth);
    }
}

doc.Save(ArtifactsDir + "BorderCollection.RemoveAllBorders.docx");
```

### Ver también

* class [BorderCollection](../)
* espacio de nombres [Aspose.Words](../../bordercollection/)
* asamblea [Aspose.Words](../../../)


