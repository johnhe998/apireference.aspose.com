---
title: DocumentBase.Styles
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentBase propiedad. Devuelve una colección de estilos definidos en el documento.
type: docs
weight: 80
url: /es/net/aspose.words/documentbase/styles/
---
## DocumentBase.Styles property

Devuelve una colección de estilos definidos en el documento.

```csharp
public StyleCollection Styles { get; }
```

### Observaciones

Para obtener más información, consulte la descripción de la[`StyleCollection`](../../stylecollection/) clase.

### Ejemplos

Muestra cómo acceder a la colección de estilos de un documento.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// Enumerar y listar todos los estilos que un documento creado usando Aspose.Words contiene por defecto.
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
```

Muestra cómo crear y utilizar un estilo de párrafo con formato de lista.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un estilo de párrafo personalizado.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Cree una lista y asegúrese de que los párrafos que usan este estilo usen esta lista.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Aplique el estilo de párrafo al párrafo actual del generador de documentos y luego agregue algo de texto.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Cambie el estilo del generador de documentos a uno que no tenga formato de lista y escriba otro párrafo.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Ver también

* class [StyleCollection](../../stylecollection/)
* class [DocumentBase](../)
* espacio de nombres [Aspose.Words](../../documentbase/)
* asamblea [Aspose.Words](../../../)


