---
title: TxtLoadOptions.TrailingSpacesOptions
second_title: Referencia de API de Aspose.Words para .NET
description: TxtLoadOptions propiedad. Obtiene o establece la opción preferida de un manejo de espacio final. El valor predeterminado esTrim .
type: docs
weight: 50
url: /es/net/aspose.words.loading/txtloadoptions/trailingspacesoptions/
---
## TxtLoadOptions.TrailingSpacesOptions property

Obtiene o establece la opción preferida de un manejo de espacio final. El valor predeterminado esTrim .

```csharp
public TxtTrailingSpacesOptions TrailingSpacesOptions { get; set; }
```

### Ejemplos

Muestra cómo recortar los espacios en blanco al cargar documentos de texto sin formato.

```csharp
string textDoc = "      Line 1 \n" +
                 "    Line 2   \n" +
                 " Line 3       ";

// Crear un objeto "TxtLoadOptions", que podemos pasar al constructor de un documento
// para modificar cómo cargamos un documento de texto sin formato.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Establecer la propiedad "LeadingSpacesOptions" en "TxtLeadingSpacesOptions.Preserve"
// para conservar todos los espacios en blanco al comienzo de cada línea.
// Establecer la propiedad "LeadingSpacesOptions" en "TxtLeadingSpacesOptions.ConvertToIndent"
// para eliminar todos los espacios en blanco del comienzo de cada línea,
// y luego aplique una sangría de primera línea izquierda al párrafo para simular el efecto de los espacios en blanco.
// Establecer la propiedad "LeadingSpacesOptions" en "TxtLeadingSpacesOptions.Trim"
// para eliminar todos los espacios en blanco del inicio de cada línea.
loadOptions.LeadingSpacesOptions = txtLeadingSpacesOptions;

// Establecer la propiedad "TrailingSpacesOptions" en "TxtTrailingSpacesOptions.Preserve"
// para conservar todos los espacios en blanco al final de cada línea. 
// Establezca la propiedad "TrailingSpacesOptions" en "TxtTrailingSpacesOptions.Trim" para 
// elimina todos los espacios en blanco del final de cada línea.
loadOptions.TrailingSpacesOptions = txtTrailingSpacesOptions;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

switch (txtLeadingSpacesOptions)
{
    case TxtLeadingSpacesOptions.ConvertToIndent:
        Assert.AreEqual(37.8d, paragraphs[0].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(25.2d, paragraphs[1].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(6.3d, paragraphs[2].ParagraphFormat.FirstLineIndent);

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
    case TxtLeadingSpacesOptions.Preserve:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("      Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("    Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith(" Line 3"));
        break;
    case TxtLeadingSpacesOptions.Trim:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
}

switch (txtTrailingSpacesOptions)
{
    case TxtTrailingSpacesOptions.Preserve:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1 \r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2   \r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3       \f"));
        break;
    case TxtTrailingSpacesOptions.Trim:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1\r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2\r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3\f"));
        break;
}
```

### Ver también

* enum [TxtTrailingSpacesOptions](../../txttrailingspacesoptions/)
* class [TxtLoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../txtloadoptions/)
* asamblea [Aspose.Words](../../../)


