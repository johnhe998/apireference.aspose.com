---
title: FontFallbackSettings.Save
second_title: Referencia de API de Aspose.Words para .NET
description: FontFallbackSettings método. Guarda la configuración de respaldo actual en la transmisión.
type: docs
weight: 50
url: /es/net/aspose.words.fonts/fontfallbacksettings/save/
---
## Save(Stream) {#save}

Guarda la configuración de respaldo actual en la transmisión.

```csharp
public void Save(Stream outputStream)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| outputStream | Stream | Salida de corriente. |

### Ejemplos

Muestra cómo cargar y guardar la configuración de reserva de fuentes en/desde una transmisión.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Cargue un documento XML que defina un conjunto de configuraciones de respaldo de fuentes.
using (FileStream fontFallbackStream = new FileStream(MyDir + "Font fallback rules.xml", FileMode.Open))
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.FallbackSettings.Load(fontFallbackStream);

    doc.FontSettings = fontSettings;
}

doc.Save(ArtifactsDir + "FontSettings.LoadFontFallbackSettingsFromStream.pdf");

// Usar una secuencia para guardar la configuración de reserva de fuente actual de nuestro documento como un documento XML.
using (FileStream fontFallbackStream =
    new FileStream(ArtifactsDir + "FallbackSettings.xml", FileMode.Create))
{
    doc.FontSettings.FallbackSettings.Save(fontFallbackStream);
}
```

### Ver también

* class [FontFallbackSettings](../)
* espacio de nombres [Aspose.Words.Fonts](../../fontfallbacksettings/)
* asamblea [Aspose.Words](../../../)

---

## Save(string) {#save_1}

Guarda la configuración de respaldo actual en el archivo.

```csharp
public void Save(string fileName)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| fileName | String | Nombre del archivo de salida. |

### Ejemplos

Muestra cómo cargar y guardar la configuración de reserva de fuentes a/desde un documento XML en el sistema de archivos local.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Cargue un documento XML que defina un conjunto de configuraciones de respaldo de fuentes.
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(MyDir + "Font fallback rules.xml");

doc.FontSettings = fontSettings;
doc.Save(ArtifactsDir + "FontSettings.LoadFontFallbackSettingsFromFile.pdf");

// Guardar la configuración de reserva de fuente actual de nuestro documento como un documento XML.
doc.FontSettings.FallbackSettings.Save(ArtifactsDir + "FallbackSettings.xml");
```

### Ver también

* class [FontFallbackSettings](../)
* espacio de nombres [Aspose.Words.Fonts](../../fontfallbacksettings/)
* asamblea [Aspose.Words](../../../)


