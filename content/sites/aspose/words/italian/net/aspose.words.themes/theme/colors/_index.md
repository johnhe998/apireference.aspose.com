---
title: Theme.Colors
second_title: Aspose.Words per .NET API Reference
description: Theme proprietà. Consente di specificare linsieme dei colori del tema per il documento.
type: docs
weight: 20
url: /it/net/aspose.words.themes/theme/colors/
---
## Theme.Colors property

Consente di specificare l'insieme dei colori del tema per il documento.

```csharp
public ThemeColors Colors { get; }
```

### Esempi

Mostra come impostare colori e caratteri personalizzati per i temi.

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// L'oggetto "Tema" ci dà accesso al tema del documento, una fonte di caratteri e colori predefiniti.
Theme theme = doc.Theme;

// Alcuni stili, come "Intestazione 1" e "Sottotitoli", erediteranno questi caratteri.
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// Anche altre lingue potrebbero avere i loro caratteri personalizzati in questo tema.
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

// La proprietà "Colori" contiene la tavolozza dei colori di Microsoft Word,
// che appare quando si cambia l'ombreggiatura o il colore del carattere.
// Applica colori personalizzati alla tavolozza dei colori in modo da accedervi facilmente in Microsoft Word
// quando, ad esempio, cambiamo il colore del carattere tramite "Home" -> "Carattere" -> "Colore del carattere",
// o inserisci una forma, quindi imposta un colore tramite "Formato forma" -> "Stili di forma".
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

// Applica colori personalizzati ai collegamenti ipertestuali negli stati cliccati e non cliccati.
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### Guarda anche

* class [ThemeColors](../../themecolors/)
* class [Theme](../)
* spazio dei nomi [Aspose.Words.Themes](../../theme/)
* assemblea [Aspose.Words](../../../)


