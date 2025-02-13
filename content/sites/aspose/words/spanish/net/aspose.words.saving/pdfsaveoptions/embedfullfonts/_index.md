---
title: PdfSaveOptions.EmbedFullFonts
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Controla cómo se incrustan las fuentes en los documentos PDF resultantes.
type: docs
weight: 100
url: /es/net/aspose.words.saving/pdfsaveoptions/embedfullfonts/
---
## PdfSaveOptions.EmbedFullFonts property

Controla cómo se incrustan las fuentes en los documentos PDF resultantes.

```csharp
public bool EmbedFullFonts { get; set; }
```

### Observaciones

El valor predeterminado es`falso`, lo que significa que las fuentes se dividen en subconjuntos antes de incrustarlas. La creación de subconjuntos es útil si desea mantener el tamaño del archivo de salida más pequeño. La creación de subconjuntos elimina all glifos no utilizados de una fuente.

Cuando este valor se establece en`verdadero`se incrusta un archivo de fuente completo en PDF sin el subconjunto . Esto dará como resultado archivos de salida más grandes, pero puede ser una opción útil cuando desee editar el PDF resultante más adelante (por ejemplo, agregar más texto).

Algunas fuentes son grandes (varios megabytes) e incrustarlas sin subsetting dará como resultado documentos de salida grandes.

### Ejemplos

Muestra cómo habilitar o deshabilitar subconjuntos al incrustar fuentes mientras se procesa un documento en PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Arvo";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Configure nuestras fuentes de fuentes para garantizar que tengamos acceso a ambas fuentes en este documento.
FontSourceBase[] originalFontsSources = FontSettings.DefaultInstance.GetFontsSources();
Aspose.Words.Fonts.FolderFontSource folderFontSource = new Aspose.Words.Fonts.FolderFontSource(FontsDir, true);
FontSettings.DefaultInstance.SetFontsSources(new[] { originalFontsSources[0], folderFontSource });

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(fontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Dado que nuestro documento contiene una fuente personalizada, puede ser deseable incrustarla en el documento de salida.
// Establezca la propiedad "EmbedFullFonts" en "true" para incrustar cada glifo de cada fuente incrustada en el PDF de salida.
// El tamaño del documento puede volverse muy grande, pero tendremos un uso completo de todas las fuentes si editamos el PDF.
// Establezca la propiedad "EmbedFullFonts" en "falso" para aplicar subconjuntos a las fuentes, guardando solo los glifos
// que el documento está usando. El archivo será considerablemente más pequeño,
// pero es posible que necesitemos acceso a fuentes personalizadas si editamos el documento.
options.EmbedFullFonts = embedFullFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf", options);

if (embedFullFonts)
    Assert.That(500000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));
else
    Assert.That(25000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));

// Restaurar las fuentes de fuentes originales.
FontSettings.DefaultInstance.SetFontsSources(originalFontsSources);
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


