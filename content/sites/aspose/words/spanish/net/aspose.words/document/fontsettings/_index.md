---
title: Document.FontSettings
second_title: Referencia de API de Aspose.Words para .NET
description: Document propiedad. Obtiene o establece la configuración de fuente del documento.
type: docs
weight: 140
url: /es/net/aspose.words/document/fontsettings/
---
## Document.FontSettings property

Obtiene o establece la configuración de fuente del documento.

```csharp
public FontSettings FontSettings { get; set; }
```

### Observaciones

Esta propiedad permite especificar la configuración de fuente por documento. Si se establece en nulo, configuración de fuente estática predeterminada [`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) se utilizará.

El valor predeterminado es nulo.

### Ejemplos

Muestra cómo configurar las reglas de sustitución de fuentes.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();

// Las fuentes de fuentes predeterminadas contienen la primera fuente que usa el documento.
Assert.AreEqual(1, fontSources.Length);
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// La segunda fuente, "Amethysta", no está disponible.
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Podemos configurar una tabla de sustitución de fuentes que determina
// qué fuentes usará Aspose.Words como sustitutos de las fuentes no disponibles.
// Establecer dos fuentes de sustitución para "Amethysta": "Arvo" y "Courier New".
// Si el primer sustituto no está disponible, Aspose.Words intenta usar el segundo sustituto y así sucesivamente.
doc.FontSettings = new FontSettings();
doc.FontSettings.SubstitutionSettings.TableSubstitution.SetSubstitutes(
    "Amethysta", new[] {"Arvo", "Courier New"});

  // "Amethysta" no está disponible y la regla de sustitución establece que la primera fuente a utilizar como sustituto es "Arvo".
Assert.False(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

  // "Arvo" tampoco está disponible, pero "Courier New" sí.
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Courier New"));

// El documento de salida mostrará el texto que usa la fuente "Amethysta" formateada con "Courier New".
doc.Save(ArtifactsDir + "FontSettings.TableSubstitution.pdf");
```

### Ver también

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


