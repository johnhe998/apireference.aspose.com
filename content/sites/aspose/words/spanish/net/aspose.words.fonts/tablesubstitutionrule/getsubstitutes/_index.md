---
title: TableSubstitutionRule.GetSubstitutes
second_title: Referencia de API de Aspose.Words para .NET
description: TableSubstitutionRule método. Devuelve una matriz que contiene nombres de fuente sustitutos para el nombre de fuente original especificado.
type: docs
weight: 20
url: /es/net/aspose.words.fonts/tablesubstitutionrule/getsubstitutes/
---
## TableSubstitutionRule.GetSubstitutes method

Devuelve una matriz que contiene nombres de fuente sustitutos para el nombre de fuente original especificado.

```csharp
public IEnumerable<string> GetSubstitutes(string originalFontName)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| originalFontName | String | Nombre de fuente original. |

### Valor_devuelto

Lista de nombres de fuentes alternativos.

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

Muestra cómo trabajar con tablas de sustitución de fuentes personalizadas.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Cree una nueva regla de sustitución de tablas y cargue la tabla de sustitución de fuentes predeterminada de Windows.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;

// Si seleccionamos fuentes exclusivamente de nuestra carpeta, necesitaremos una tabla de sustitución personalizada.
// Ya no tendremos acceso a las fuentes de Microsoft Windows,
// como "Arial" o "Times New Roman" ya que no existen en nuestra nueva carpeta de fuentes.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// A continuación se muestran dos formas de cargar una tabla de sustitución desde un archivo en el sistema de archivos local.
// 1 - De un flujo:
using (FileStream fileStream = new FileStream(MyDir + "Font substitution rules.xml", FileMode.Open))
{
    tableSubstitutionRule.Load(fileStream);
}

// 2 - Directamente desde un archivo:
tableSubstitutionRule.Load(MyDir + "Font substitution rules.xml");

// Como ya no tenemos acceso a "Arial", nuestra tabla de fuentes primero intentará sustituirla por "Fuente inexistente".
// No tenemos esta fuente, por lo que pasará al siguiente sustituto, "Kreon", que se encuentra en la carpeta "MyFonts".
Assert.AreEqual(new[] {"Missing Font", "Kreon"}, tableSubstitutionRule.GetSubstitutes("Arial").ToArray());

// Podemos expandir esta tabla programáticamente. Añadiremos una entrada que sustituya "Times New Roman" por "Arvo"
Assert.Null(tableSubstitutionRule.GetSubstitutes("Times New Roman"));
tableSubstitutionRule.AddSubstitutes("Times New Roman", "Arvo");
Assert.AreEqual(new[] {"Arvo"}, tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// Podemos agregar un sustituto alternativo secundario para una entrada de fuente existente con AddSubstitutes().
// En caso de que "Arvo" no esté disponible, nuestra tabla buscará "M+ 2m" como segunda opción sustituta.
tableSubstitutionRule.AddSubstitutes("Times New Roman", "M+ 2m");
Assert.AreEqual(new[] {"Arvo", "M+ 2m"}, tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// SetSubstitutes() puede establecer una nueva lista de fuentes sustitutas para una fuente.
tableSubstitutionRule.SetSubstitutes("Times New Roman", new[] {"Squarish Sans CT", "M+ 2m"});
Assert.AreEqual(new[] {"Squarish Sans CT", "M+ 2m"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// Escribir texto en fuentes a las que no tenemos acceso invocará nuestras reglas de sustitución.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("Text written in Arial, to be substituted by Kreon.");

builder.Font.Name = "Times New Roman";
builder.Writeln("Text written in Times New Roman, to be substituted by Squarish Sans CT.");

doc.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Custom.pdf");
```

### Ver también

* class [TableSubstitutionRule](../)
* espacio de nombres [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* asamblea [Aspose.Words](../../../)


