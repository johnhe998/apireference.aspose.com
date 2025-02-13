---
title: Class ThemeFonts
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Themes.ThemeFonts clase. Representa una colección de fuentes en el esquema de fuentes lo que permite especificar diferentes fuentes para diferentes idiomasLatin EastAsian yComplexScript .
type: docs
weight: 6200
url: /es/net/aspose.words.themes/themefonts/
---
## ThemeFonts class

Representa una colección de fuentes en el esquema de fuentes, lo que permite especificar diferentes fuentes para diferentes idiomas[`Latin`](./latin/) ,[`EastAsian`](./eastasian/) y[`ComplexScript`](./complexscript/) .

```csharp
public class ThemeFonts
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [ComplexScript](../../aspose.words.themes/themefonts/complexscript/) { get; set; } | Especifica el nombre de la fuente para los caracteres ComplexScript. |
| [EastAsian](../../aspose.words.themes/themefonts/eastasian/) { get; set; } | Especifica el nombre de la fuente para los caracteres de Asia oriental. |
| [Latin](../../aspose.words.themes/themefonts/latin/) { get; set; } | Especifica el nombre de la fuente para los caracteres latinos. |

### Ejemplos

Muestra cómo establecer colores y fuentes personalizados para los temas.

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// El objeto "Tema" nos da acceso al tema del documento, una fuente de fuentes y colores predeterminados.
Theme theme = doc.Theme;

// Algunos estilos, como "Título 1" y "Subtítulo", heredarán estas fuentes.
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// Otros idiomas también pueden tener sus fuentes personalizadas en este tema.
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

// La propiedad "Colores" contiene la paleta de colores de Microsoft Word,
// que aparece al cambiar el sombreado o el color de la fuente.
// Aplique colores personalizados a la paleta de colores para que tengamos fácil acceso a ellos en Microsoft Word
// cuando, por ejemplo, cambiamos el color de la fuente a través de "Inicio" -> "Fuente" -> "Color de fuente",
// o inserte una forma, y luego establezca un color para ella a través de "Formato de forma" -> "Estilos de forma".
ThemeColors colors = theme.Colors;
colors.Dark1 = Color.MidnightBlue;
colors.Light1 = Color.PaleGreen;
colors.Dark2 = Color.Indigo;
colors.Light2 = Color.Khaki;

colors.Accent1 = Color.OrangeRed;
colors.Accent2 = Color.LightSalmon;
colors.Accent3 = Color.Yellow;
colors.Accent4 = Color.Gold;
colors.Accent5 = Color.BlueViolet;
colors.Accent6 = Color.DarkViolet;

// Aplique colores personalizados a los hipervínculos en sus estados de clic y no clic.
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### Ver también

* espacio de nombres [Aspose.Words.Themes](../../aspose.words.themes/)
* asamblea [Aspose.Words](../../)


