---
title: HtmlFixedSaveOptions.UseTargetMachineFonts
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlFixedSaveOptions propiedad. Indicador indica si se deben usar fuentes de la máquina de destino para mostrar el documento. Si este indicador se establece en verdaderoFontFormat yExportEmbeddedFontspropiedades no tienen efecto tambiénResourceSavingCallback no se activa para fonts. El valor predeterminado es false.
type: docs
weight: 190
url: /es/net/aspose.words.saving/htmlfixedsaveoptions/usetargetmachinefonts/
---
## HtmlFixedSaveOptions.UseTargetMachineFonts property

Indicador indica si se deben usar fuentes de la máquina de destino para mostrar el documento. Si este indicador se establece en verdadero,[`FontFormat`](../fontformat/) y[`ExportEmbeddedFonts`](../exportembeddedfonts/)propiedades no tienen efecto, también[`ResourceSavingCallback`](../resourcesavingcallback/) no se activa para fonts. El valor predeterminado es false.

```csharp
public bool UseTargetMachineFonts { get; set; }
```

### Ejemplos

Muestra cómo usar fuentes solo de la máquina de destino al guardar un documento en HTML.

```csharp
Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedCss = true,
    UseTargetMachineFonts = useTargetMachineFonts,
    FontFormat = ExportFontFormat.Ttf,
    ExportEmbeddedFonts = false,
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html");

if (useTargetMachineFonts)
    Assert.False(Regex.Match(outDocContents, "@font-face").Success);
else
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], " +
        "url[(]'HtmlFixedSaveOptions.UsingMachineFonts/font001.ttf'[)] format[(]'truetype'[)]; }").Success);
```

### Ver también

* class [HtmlFixedSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* asamblea [Aspose.Words](../../../)


