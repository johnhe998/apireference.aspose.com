---
title: DocumentBuilder.PushFont
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentBuilder método. Guarda el formato de carácter actual en la pila.
type: docs
weight: 570
url: /es/net/aspose.words/documentbuilder/pushfont/
---
## DocumentBuilder.PushFont method

Guarda el formato de carácter actual en la pila.

```csharp
public void PushFont()
```

### Ejemplos

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

* property [Font](../font/)
* method [PopFont](../popfont/)
* class [DocumentBuilder](../)
* espacio de nombres [Aspose.Words](../../documentbuilder/)
* asamblea [Aspose.Words](../../../)


