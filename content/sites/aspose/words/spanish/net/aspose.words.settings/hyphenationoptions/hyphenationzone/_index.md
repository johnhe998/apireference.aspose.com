---
title: HyphenationOptions.HyphenationZone
second_title: Referencia de API de Aspose.Words para .NET
description: HyphenationOptions propiedad. Obtiene o establece la distancia en 1/20 de un punto desde el margen derecho dentro del cual no desea dividir palabras. El valor predeterminado para esta propiedad es 360 025 pulgadas.
type: docs
weight: 50
url: /es/net/aspose.words.settings/hyphenationoptions/hyphenationzone/
---
## HyphenationOptions.HyphenationZone property

Obtiene o establece la distancia en 1/20 de un punto desde el margen derecho dentro del cual no desea dividir palabras. El valor predeterminado para esta propiedad es 360 (0,25 pulgadas).

```csharp
public int HyphenationZone { get; set; }
```

### Ejemplos

Muestra cómo configurar la partición automática.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.HyphenationOptions.AutoHyphenation = true;
doc.HyphenationOptions.ConsecutiveHyphenLimit = 2;
doc.HyphenationOptions.HyphenationZone = 720;
doc.HyphenationOptions.HyphenateCaps = true;

doc.Save(ArtifactsDir + "Document.HyphenationOptions.docx");
```

### Ver también

* class [HyphenationOptions](../)
* espacio de nombres [Aspose.Words.Settings](../../hyphenationoptions/)
* asamblea [Aspose.Words](../../../)


