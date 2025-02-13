---
title: FontSourceBase.WarningCallback
second_title: Referencia de API de Aspose.Words para .NET
description: FontSourceBase propiedad. Llamado durante el procesamiento del origen de la fuente cuando se detecta un problema que podría resultar en la pérdida de fidelidad del formato.
type: docs
weight: 30
url: /es/net/aspose.words.fonts/fontsourcebase/warningcallback/
---
## FontSourceBase.WarningCallback property

Llamado durante el procesamiento del origen de la fuente cuando se detecta un problema que podría resultar en la pérdida de fidelidad del formato.

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### Ejemplos

Muestra cómo llamar a la devolución de llamada de advertencia cuando las fuentes de fuente están trabajando.

```csharp
[Test]
public void FontSourceWarning()
{
    FontSettings settings = new FontSettings();
    settings.SetFontsFolder("bad folder?", false);

    FontSourceBase source = settings.GetFontsSources()[0];
    FontSourceWarningCollector callback = new FontSourceWarningCollector();
    source.WarningCallback = callback;

    // Obtener la lista de fuentes para llamar devolución de llamada de advertencia.
    IList<PhysicalFontInfo> fontInfos = source.GetAvailableFonts();

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Contains("Error loading font from the folder \"bad folder?\""));
}

private class FontSourceWarningCollector : IWarningCallback
{
    /// <summary>
    /// Se llama cada vez que se produce una advertencia durante el procesamiento del origen de la fuente.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        FontSubstitutionWarnings.Warning(info);
    }

    public readonly WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

### Ver también

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [FontSourceBase](../)
* espacio de nombres [Aspose.Words.Fonts](../../fontsourcebase/)
* asamblea [Aspose.Words](../../../)


