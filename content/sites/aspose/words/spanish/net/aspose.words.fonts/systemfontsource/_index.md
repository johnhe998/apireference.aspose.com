---
title: Class SystemFontSource
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fonts.SystemFontSource clase. Representa todas las fuentes TrueType instaladas en el sistema.
type: docs
weight: 2870
url: /es/net/aspose.words.fonts/systemfontsource/
---
## SystemFontSource class

Representa todas las fuentes TrueType instaladas en el sistema.

```csharp
public class SystemFontSource : FontSourceBase
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [SystemFontSource](systemfontsource/#constructor)() | Director |
| [SystemFontSource](systemfontsource/#constructor_1)(int) | Director |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Devuelve la prioridad de origen de la fuente. |
| override [Type](../../aspose.words.fonts/systemfontsource/type/) { get; } | Devuelve el tipo de fuente fuente. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Llamado durante el procesamiento del origen de la fuente cuando se detecta un problema que podría resultar en la pérdida de fidelidad del formato. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Devuelve la lista de fuentes disponibles a través de esta fuente. |
| static [GetSystemFontFolders](../../aspose.words.fonts/systemfontsource/getsystemfontfolders/)() | Devuelve las carpetas de fuentes del sistema o una matriz vacía si no se puede acceder a las carpetas. |

### Ejemplos

Muestra cómo acceder a la fuente de fuentes del sistema de un documento y establecer fuentes sustitutas.

```csharp
Document doc = new Document();
doc.FontSettings = new FontSettings();

// De forma predeterminada, un documento en blanco siempre contiene una fuente de fuente del sistema.
Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);

SystemFontSource systemFontSource = (SystemFontSource) doc.FontSettings.GetFontsSources()[0];
Assert.AreEqual(FontSourceType.SystemFonts, systemFontSource.Type);
Assert.AreEqual(0, systemFontSource.Priority);

PlatformID pid = Environment.OSVersion.Platform;
bool isWindows = (pid == PlatformID.Win32NT) || (pid == PlatformID.Win32S) ||
                 (pid == PlatformID.Win32Windows) || (pid == PlatformID.WinCE);
if (isWindows)
{
    const string fontsPath = @"C:\WINDOWS\Fonts";
    Assert.AreEqual(fontsPath.ToLower(),
        SystemFontSource.GetSystemFontFolders().FirstOrDefault()?.ToLower());
}

foreach (string systemFontFolder in SystemFontSource.GetSystemFontFolders())
{
    Console.WriteLine(systemFontFolder);
}

// Establecer una fuente que existe en el directorio de fuentes de Windows como sustituto de una que no existe.
doc.FontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;
doc.FontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Kreon-Regular", new[] {"Calibri"});

Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
Assert.Contains("Calibri",
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").ToArray());

// Alternativamente, podríamos agregar una fuente de fuente de carpeta en la que la carpeta correspondiente contenga la fuente.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
doc.FontSettings.SetFontsSources(new FontSourceBase[] {systemFontSource, folderFontSource});
Assert.AreEqual(2, doc.FontSettings.GetFontsSources().Length);

// Restablecer las fuentes de fuente aún nos deja con la fuente de fuente del sistema, así como con nuestros sustitutos.
doc.FontSettings.ResetFontSources();

Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);
Assert.AreEqual(FontSourceType.SystemFonts, doc.FontSettings.GetFontsSources()[0].Type);
Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
```

### Ver también

* class [FontSourceBase](../fontsourcebase/)
* espacio de nombres [Aspose.Words.Fonts](../../aspose.words.fonts/)
* asamblea [Aspose.Words](../../)


