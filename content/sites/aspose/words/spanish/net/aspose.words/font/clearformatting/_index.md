---
title: Font.ClearFormatting
second_title: Referencia de API de Aspose.Words para .NET
description: Font método. Restablece el formato de fuente predeterminado.
type: docs
weight: 550
url: /es/net/aspose.words/font/clearformatting/
---
## Font.ClearFormatting method

Restablece el formato de fuente predeterminado.

```csharp
public void ClearFormatting()
```

### Observaciones

Elimina todo el formato de fuente especificado explícitamente en el objeto desde which  **Fuente** se obtuvo por lo que el formato de fuente se heredará de el padre apropiado.

### Ejemplos

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

### Ver también

* class [Font](../)
* espacio de nombres [Aspose.Words](../../font/)
* asamblea [Aspose.Words](../../../)


