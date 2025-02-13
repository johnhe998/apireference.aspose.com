---
title: FontSettings.SetFontsFolder
second_title: Aspose.Words per .NET API Reference
description: FontSettings metodo. Imposta la cartella in cui Aspose.Words cerca i caratteri TrueType durante il rendering di documenti o lincorporamento di caratteri. Questa è una scorciatoia perSetFontsFolders per impostare una sola directory di font.
type: docs
weight: 80
url: /it/net/aspose.words.fonts/fontsettings/setfontsfolder/
---
## FontSettings.SetFontsFolder method

Imposta la cartella in cui Aspose.Words cerca i caratteri TrueType durante il rendering di documenti o l'incorporamento di caratteri. Questa è una scorciatoia per[`SetFontsFolders`](../setfontsfolders/) per impostare una sola directory di font.

```csharp
public void SetFontsFolder(string fontFolder, bool recursive)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| fontFolder | String | La cartella che contiene i caratteri TrueType. |
| recursive | Boolean | True per eseguire la scansione ricorsiva delle cartelle specificate per i caratteri. |

### Esempi

Mostra come impostare una directory di origine dei caratteri.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arvo";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Le nostre fonti di font non contengono il font che abbiamo usato per il testo in questo documento.
// Se utilizziamo queste impostazioni dei caratteri durante il rendering di questo documento,
// Aspose.Words applicherà un font di fallback al testo che ha un font che Aspose.Words non riesce a individuare.
FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);
Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Nelle fonti di carattere predefinite mancano i due caratteri che stiamo utilizzando in questo documento.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Usa il metodo "SetFontsFolder" per impostare una directory che agirà come una nuova fonte di font.
// Passa "false" come argomento "ricorsivo" per includere i caratteri da tutti i file dei caratteri che si trovano nella directory
// che stiamo passando nel primo argomento, ma non includi alcun font in nessuna delle sottocartelle di quella directory.
// Passa "true" come argomento "ricorsivo" per includere tutti i file di font nella directory che stiamo passando
// nel primo argomento, così come tutti i caratteri nelle sue sottodirectory.
FontSettings.DefaultInstance.SetFontsFolder(FontsDir, recursive);

FontSourceBase[] newFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, newFontSources.Length);
Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Il font "Amethysta" si trova in una sottocartella della directory dei font.
if (recursive)
{
    Assert.AreEqual(25, newFontSources[0].GetAvailableFonts().Count);
    Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}
else
{
    Assert.AreEqual(18, newFontSources[0].GetAvailableFonts().Count);
    Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}

doc.Save(ArtifactsDir + "FontSettings.SetFontsFolder.pdf");

// Ripristina le origini dei caratteri originali.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### Guarda anche

* class [FontSettings](../)
* spazio dei nomi [Aspose.Words.Fonts](../../fontsettings/)
* assemblea [Aspose.Words](../../../)


