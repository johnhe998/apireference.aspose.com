---
title: LoadOptions.FontSettings
second_title: Referencia de API de Aspose.Words para .NET
description: LoadOptions propiedad. Permite especificar la configuración de la fuente del documento.
type: docs
weight: 70
url: /es/net/aspose.words.loading/loadoptions/fontsettings/
---
## LoadOptions.FontSettings property

Permite especificar la configuración de la fuente del documento.

```csharp
public FontSettings FontSettings { get; set; }
```

### Observaciones

Al cargar algunos formatos, Aspose.Words puede requerir resolver las fuentes. Por ejemplo, al cargar documentos HTML, Aspose.Words puede resolver las fuentes para realizar una reserva de fuentes.

Si se establece en nulo, configuración de fuente estática predeterminada[`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) se utilizará.

El valor predeterminado es nulo.

### Ejemplos

Muestra cómo aplicar la configuración de sustitución de fuentes al cargar un documento.

```csharp
// Crear un objeto FontSettings que sustituirá la fuente "Times New Roman"
// con la fuente "Arvo" de nuestra carpeta "MyFonts".
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(FontsDir, false);
fontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Times New Roman", "Arvo");

// Establecer ese objeto FontSettings como una propiedad de un objeto LoadOptions recién creado.
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;

// Cargue el documento, luego reprodúzcalo como PDF con la sustitución de fuente.
Document doc = new Document(MyDir + "Document.docx", loadOptions);

doc.Save(ArtifactsDir + "LoadOptions.FontSettings.pdf");
```

Muestra cómo designar fuentes sustitutas durante la carga.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();

// Establecer una regla de sustitución de fuentes para un objeto LoadOptions.
// Si el documento que estamos cargando usa una fuente que no tenemos,
// esta regla sustituirá la fuente no disponible por una que sí existe.
// En este caso, todos los usos de "MissingFont" se convertirán a "Comic Sans MS".
TableSubstitutionRule substitutionRule = loadOptions.FontSettings.SubstitutionSettings.TableSubstitution;
substitutionRule.AddSubstitutes("MissingFont", new[] {"Comic Sans MS"});

Document doc = new Document(MyDir + "Missing font.html", loadOptions);

// En este punto, dicho texto seguirá estando en "MissingFont".
// La sustitución de fuentes tendrá lugar cuando rendericemos el documento.
Assert.AreEqual("MissingFont", doc.FirstSection.Body.FirstParagraph.Runs[0].Font.Name);

doc.Save(ArtifactsDir + "FontSettings.ResolveFontsBeforeLoadingDocument.pdf");
```

### Ver también

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [LoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../loadoptions/)
* asamblea [Aspose.Words](../../../)


