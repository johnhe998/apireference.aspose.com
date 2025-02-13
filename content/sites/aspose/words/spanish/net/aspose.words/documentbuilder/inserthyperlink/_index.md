---
title: DocumentBuilder.InsertHyperlink
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentBuilder método. Inserta un hipervínculo en el documento.
type: docs
weight: 340
url: /es/net/aspose.words/documentbuilder/inserthyperlink/
---
## DocumentBuilder.InsertHyperlink method

Inserta un hipervínculo en el documento.

```csharp
public Field InsertHyperlink(string displayText, string urlOrBookmark, bool isBookmark)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| displayText | String | Texto del enlace que se mostrará en el documento. |
| urlOrBookmark | String | Enlace de destino. Puede ser una url o el nombre de un marcador dentro del documento. Este método siempre agrega apóstrofes al principio y al final de la url. |
| isBookmark | Boolean | True si el parámetro anterior es el nombre de un marcador dentro del documento; false si el parámetro anterior es una URL. |

### Valor_devuelto

A[`Field`](../../../aspose.words.fields/field/) objeto que representa el campo insertado.

### Observaciones

Tenga en cuenta que debe especificar el formato de fuente para el texto de visualización del hipervínculo explícitamente utilizando el[`Font`](../font/) propiedad.

Este método llama internamente[`InsertField`](../insertfield/) para insertar un HIPERVINCULO de MS Word field en el documento.

### Ejemplos

Muestra cómo insertar un hipervínculo que hace referencia a un marcador local.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("Bookmark1");
builder.Write("Bookmarked text. ");
builder.EndBookmark("Bookmark1");
builder.Writeln("Text outside of the bookmark.");

// Inserta un campo de HIPERVÍNCULO que se vincule al marcador. Podemos pasar interruptores de campo
// al método "InsertHyperlink" como parte del argumento que contiene el nombre del marcador al que se hace referencia.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Link to Bookmark1", @"Bookmark1"" \o ""Hyperlink Tip", true);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlinkToLocalBookmark.docx");
```

Muestra cómo insertar un campo de hipervínculo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("For more information, please visit the ");

// Inserte un hipervínculo y enfatícelo con un formato personalizado.
// El hipervínculo será un fragmento de texto en el que se puede hacer clic y que nos llevará a la ubicación especificada en la URL.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Google website", "https://www.google.com", falso);
builder.Font.ClearFormatting();
builder.Writeln(".");

// Ctrl + clic izquierdo en el enlace del texto en Microsoft Word nos llevará a la URL a través de una nueva ventana del navegador web.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlink.docx");
```

Muestra cómo utilizar la pila de formato de un generador de documentos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Configure el formato de fuente, luego escriba el texto que va antes del hipervínculo.
builder.Font.Name = "Arial";
builder.Font.Size = 24;
builder.Write("To visit Google, hold Ctrl and click ");

// Conservar nuestra configuración de formato actual en la pila.
builder.PushFont();

// Altere el formato actual del constructor aplicando un nuevo estilo.
builder.Font.StyleIdentifier = StyleIdentifier.Hyperlink;
builder.InsertHyperlink("here", "http://www.google.com", falso);

Assert.AreEqual(Color.Blue.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.Single, builder.Font.Underline);

// Restaure el formato de fuente que guardamos anteriormente y elimine el elemento de la pila.
builder.PopFont();

Assert.AreEqual(Color.Empty.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.None, builder.Font.Underline);

builder.Write(". We hope you enjoyed the example.");

doc.Save(ArtifactsDir + "DocumentBuilder.PushPopFont.docx");
```

### Ver también

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)


