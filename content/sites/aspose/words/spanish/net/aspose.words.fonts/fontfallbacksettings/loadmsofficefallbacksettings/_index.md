---
title: FontFallbackSettings.LoadMsOfficeFallbackSettings
second_title: Referencia de API de Aspose.Words para .NET
description: FontFallbackSettings método. Carga la configuración de respaldo predefinida que imita el respaldo de Microsoft Word y usa las fuentes de Microsoft Office.
type: docs
weight: 30
url: /es/net/aspose.words.fonts/fontfallbacksettings/loadmsofficefallbacksettings/
---
## FontFallbackSettings.LoadMsOfficeFallbackSettings method

Carga la configuración de respaldo predefinida que imita el respaldo de Microsoft Word y usa las fuentes de Microsoft Office.

```csharp
public void LoadMsOfficeFallbackSettings()
```

### Ejemplos

Muestra cómo cargar la configuración de fuente alternativa predefinida.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Guarde el esquema de fuente alternativo predeterminado en un documento XML.
// Por ejemplo, uno de los elementos tiene un valor de "0C00-0C7F" para Range y un valor "Vani" correspondiente para FallbackFonts.
// Esto significa que si la fuente que está usando algún texto no tiene símbolos para el bloque Unicode 0x0C00-0x0C7F,
// el esquema alternativo utilizará símbolos del sustituto de fuente "Vani".
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.Default.xml");

// A continuación se muestran dos esquemas alternativos de fuente predefinidos entre los que podemos elegir.
// 1 - Usar el esquema predeterminado de Microsoft Office, que es el mismo que el predeterminado:
fontFallbackSettings.LoadMsOfficeFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadMsOfficeFallbackSettings.xml");

// 2 - Usa el esquema creado a partir de las fuentes Google Noto:
fontFallbackSettings.LoadNotoFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadNotoFallbackSettings.xml");
```

### Ver también

* class [FontFallbackSettings](../)
* espacio de nombres [Aspose.Words.Fonts](../../fontfallbacksettings/)
* asamblea [Aspose.Words](../../../)


