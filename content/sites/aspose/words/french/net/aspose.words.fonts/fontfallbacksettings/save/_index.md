---
title: FontFallbackSettings.Save
second_title: Référence de l'API Aspose.Words pour .NET
description: FontFallbackSettings méthode. Enregistre les paramètres de secours actuels dans le flux.
type: docs
weight: 50
url: /fr/net/aspose.words.fonts/fontfallbacksettings/save/
---
## Save(Stream) {#save}

Enregistre les paramètres de secours actuels dans le flux.

```csharp
public void Save(Stream outputStream)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| outputStream | Stream | Flux de sortie. |

### Exemples

Montre comment charger et enregistrer les paramètres de remplacement des polices vers/depuis un flux.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Charge un document XML qui définit un ensemble de paramètres de remplacement de police.
using (FileStream fontFallbackStream = new FileStream(MyDir + "Font fallback rules.xml", FileMode.Open))
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.FallbackSettings.Load(fontFallbackStream);

    doc.FontSettings = fontSettings;
}

doc.Save(ArtifactsDir + "FontSettings.LoadFontFallbackSettingsFromStream.pdf");

// Utilisez un flux pour enregistrer les paramètres de remplacement de police actuels de notre document en tant que document XML.
using (FileStream fontFallbackStream =
    new FileStream(ArtifactsDir + "FallbackSettings.xml", FileMode.Create))
{
    doc.FontSettings.FallbackSettings.Save(fontFallbackStream);
}
```

### Voir également

* class [FontFallbackSettings](../)
* espace de noms [Aspose.Words.Fonts](../../fontfallbacksettings/)
* Assemblée [Aspose.Words](../../../)

---

## Save(string) {#save_1}

Enregistre les paramètres de secours actuels dans le fichier.

```csharp
public void Save(string fileName)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| fileName | String | Nom du fichier de sortie. |

### Exemples

Montre comment charger et enregistrer les paramètres de remplacement des polices vers/depuis un document XML dans le système de fichiers local.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Charge un document XML qui définit un ensemble de paramètres de remplacement de police.
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(MyDir + "Font fallback rules.xml");

doc.FontSettings = fontSettings;
doc.Save(ArtifactsDir + "FontSettings.LoadFontFallbackSettingsFromFile.pdf");

// Enregistrez les paramètres de remplacement de police actuels de notre document en tant que document XML.
doc.FontSettings.FallbackSettings.Save(ArtifactsDir + "FallbackSettings.xml");
```

### Voir également

* class [FontFallbackSettings](../)
* espace de noms [Aspose.Words.Fonts](../../fontfallbacksettings/)
* Assemblée [Aspose.Words](../../../)


