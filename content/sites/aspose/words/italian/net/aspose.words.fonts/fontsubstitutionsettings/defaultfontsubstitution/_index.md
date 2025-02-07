---
title: FontSubstitutionSettings.DefaultFontSubstitution
second_title: Aspose.Words per .NET API Reference
description: FontSubstitutionSettings proprietà. Impostazioni relative alla regola di sostituzione dei caratteri predefinita.
type: docs
weight: 10
url: /it/net/aspose.words.fonts/fontsubstitutionsettings/defaultfontsubstitution/
---
## FontSubstitutionSettings.DefaultFontSubstitution property

Impostazioni relative alla regola di sostituzione dei caratteri predefinita.

```csharp
public DefaultFontSubstitutionRule DefaultFontSubstitution { get; }
```

### Esempi

Mostra come impostare la regola di sostituzione dei caratteri predefinita.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Ottieni la regola di sostituzione predefinita all'interno di FontSettings.
// Questa regola sostituirà tutti i caratteri mancanti con "Times New Roman".
DefaultFontSubstitutionRule defaultFontSubstitutionRule =
    fontSettings.SubstitutionSettings.DefaultFontSubstitution;
Assert.True(defaultFontSubstitutionRule.Enabled);
Assert.AreEqual("Times New Roman", defaultFontSubstitutionRule.DefaultFontName);

// Imposta il carattere sostitutivo predefinito su "Courier New".
defaultFontSubstitutionRule.DefaultFontName = "Courier New";

// Usando un generatore di documenti, aggiungi del testo in un font di cui non dobbiamo vedere la sostituzione,
// e quindi renderizza il risultato in un PDF.
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Missing Font";
builder.Writeln("Line written in a missing font, which will be substituted with Courier New.");

doc.Save(ArtifactsDir + "FontSettings.DefaultFontSubstitutionRule.pdf");
```

### Guarda anche

* class [DefaultFontSubstitutionRule](../../defaultfontsubstitutionrule/)
* class [FontSubstitutionSettings](../)
* spazio dei nomi [Aspose.Words.Fonts](../../fontsubstitutionsettings/)
* assemblea [Aspose.Words](../../../)


