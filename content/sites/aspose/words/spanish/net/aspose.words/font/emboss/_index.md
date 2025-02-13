---
title: Font.Emboss
second_title: Referencia de API de Aspose.Words para .NET
description: Font propiedad. Verdadero si la fuente tiene formato de relieve.
type: docs
weight: 100
url: /es/net/aspose.words/font/emboss/
---
## Font.Emboss property

Verdadero si la fuente tiene formato de relieve.

```csharp
public bool Emboss { get; set; }
```

### Ejemplos

Muestra cómo aplicar efectos de grabado/relieve al texto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.Color = Color.LightBlue;

// A continuación hay dos formas de usar sombras para aplicar un efecto similar al 3D al texto.
// 1 - Grabe el texto para que parezca que las letras están hundidas en la página:
builder.Font.Engrave = true;

builder.Writeln("This text is engraved.");

// 2 - Realce el texto para que parezca que las letras salen de la página:
builder.Font.Engrave = false;
builder.Font.Emboss = true;

builder.Writeln("This text is embossed.");

doc.Save(ArtifactsDir + "Font.EngraveEmboss.docx");
```

### Ver también

* class [Font](../)
* espacio de nombres [Aspose.Words](../../font/)
* asamblea [Aspose.Words](../../../)


