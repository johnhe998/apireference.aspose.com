---
title: HyphenationOptions.AutoHyphenation
second_title: Referencia de API de Aspose.Words para .NET
description: HyphenationOptions propiedad. Obtiene o establece el valor que determina si la partición automática está activada para el documento. El valor predeterminado para esta propiedad es falso .
type: docs
weight: 20
url: /es/net/aspose.words.settings/hyphenationoptions/autohyphenation/
---
## HyphenationOptions.AutoHyphenation property

Obtiene o establece el valor que determina si la partición automática está activada para el documento. El valor predeterminado para esta propiedad es **falso** .

```csharp
public bool AutoHyphenation { get; set; }
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


