---
title: Enum ThemeColor
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Themes.ThemeColor enum. Specifica i colori del tema per i temi del documento.
type: docs
weight: 6170
url: /it/net/aspose.words.themes/themecolor/
---
## ThemeColor enumeration

Specifica i colori del tema per i temi del documento.

```csharp
public enum ThemeColor
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `-1` | Nessun colore. |
| Dark1 | `0` | Colore principale scuro 1. |
| Light1 | `1` | Colore principale chiaro 1. |
| Dark2 | `2` | Colore principale scuro 2. |
| Light2 | `3` | Colore principale chiaro 2. |
| Accent1 | `4` | Colore accento 1. |
| Accent2 | `5` | Colore accento 2. |
| Accent3 | `6` | Colore accento 3. |
| Accent4 | `7` | Colore accento 4. |
| Accent5 | `8` | Colore accento 5. |
| Accent6 | `9` | Colore accento 6. |
| Hyperlink | `10` | Colore collegamento ipertestuale. |
| FollowedHyperlink | `11` | Colore collegamento ipertestuale seguito. |
| Text1 | `12` | Colore testo 1. |
| Text2 | `13` | Colore testo 2. |
| Background1 | `14` | Colore di sfondo 1. |
| Background2 | `15` | Colore di sfondo 2. |

### Osservazioni

Il colore del tema specificato è un riferimento a uno dei colori del tema predefiniti, situato nella parte del tema del documento , che consente di impostare le informazioni sul colore a livello centrale nel documento.

### Esempi

Mostra come creare e utilizzare uno stile a tema.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Crea uno stile con le proprietà dei caratteri del tema.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

Mostra come lavorare con i caratteri e i colori del tema.

```csharp
Document doc = new Document();

// Definisci i caratteri per le lingue utilizzate per impostazione predefinita.
doc.Theme.MinorFonts.Latin = "Algerian";
doc.Theme.MinorFonts.EastAsian = "Aharoni";
doc.Theme.MinorFonts.ComplexScript = "Andalus";

Font font = doc.Styles["Normal"].Font;
Console.WriteLine("Originally the Normal style theme color is: {0} and RGB color is: {1}\n", font.ThemeColor, font.Color);

// Possiamo usare il carattere e il colore del tema invece dei valori predefiniti.
font.ThemeFont = ThemeFont.Minor;
font.ThemeColor = ThemeColor.Accent2;

Assert.AreEqual(ThemeFont.Minor, font.ThemeFont);
Assert.AreEqual("Algerian", font.Name);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontAscii);
Assert.AreEqual("Algerian", font.NameAscii);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontBi);
Assert.AreEqual("Andalus", font.NameBi);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontFarEast);
Assert.AreEqual("Aharoni", font.NameFarEast);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontOther);
Assert.AreEqual("Algerian", font.NameOther);

Assert.AreEqual(ThemeColor.Accent2, font.ThemeColor);
Assert.AreEqual(Color.Empty, font.Color);

// Esistono diversi modi per reimpostarli font e colore.
// 1 - Impostando ThemeFont.None/ThemeColor.None:
font.ThemeFont = ThemeFont.None;
font.ThemeColor = ThemeColor.None;

Assert.AreEqual(ThemeFont.None, font.ThemeFont);
Assert.AreEqual("Algerian", font.Name);

Assert.AreEqual(ThemeFont.None, font.ThemeFontAscii);
Assert.AreEqual("Algerian", font.NameAscii);

Assert.AreEqual(ThemeFont.None, font.ThemeFontBi);
Assert.AreEqual("Andalus", font.NameBi);

Assert.AreEqual(ThemeFont.None, font.ThemeFontFarEast);
Assert.AreEqual("Aharoni", font.NameFarEast);

Assert.AreEqual(ThemeFont.None, font.ThemeFontOther);
Assert.AreEqual("Algerian", font.NameOther);

Assert.AreEqual(ThemeColor.None, font.ThemeColor);
Assert.AreEqual(Color.Empty, font.Color);

// 2 - Impostando nomi di caratteri/colori non tematici:
font.Name = "Arial";
font.Color = Color.Blue;

Assert.AreEqual(ThemeFont.None, font.ThemeFont);
Assert.AreEqual("Arial", font.Name);

Assert.AreEqual(ThemeFont.None, font.ThemeFontAscii);
Assert.AreEqual("Arial", font.NameAscii);

Assert.AreEqual(ThemeFont.None, font.ThemeFontBi);
Assert.AreEqual("Arial", font.NameBi);

Assert.AreEqual(ThemeFont.None, font.ThemeFontFarEast);
Assert.AreEqual("Arial", font.NameFarEast);

Assert.AreEqual(ThemeFont.None, font.ThemeFontOther);
Assert.AreEqual("Arial", font.NameOther);

Assert.AreEqual(ThemeColor.None, font.ThemeColor);
Assert.AreEqual(Color.Blue.ToArgb(), font.Color.ToArgb());
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Themes](../../aspose.words.themes/)
* assemblea [Aspose.Words](../../)


