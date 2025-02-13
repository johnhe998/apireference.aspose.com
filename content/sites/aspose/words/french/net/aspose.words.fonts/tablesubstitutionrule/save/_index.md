---
title: TableSubstitutionRule.Save
second_title: Référence de l'API Aspose.Words pour .NET
description: TableSubstitutionRule méthode. Enregistre les paramètres de substitution de table actuels dans le fichier.
type: docs
weight: 70
url: /fr/net/aspose.words.fonts/tablesubstitutionrule/save/
---
## Save(string) {#save_1}

Enregistre les paramètres de substitution de table actuels dans le fichier.

```csharp
public void Save(string fileName)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| fileName | String | Nom du fichier de sortie. |

### Exemples

Montre comment accéder aux tables de substitution de polices pour Windows et Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Crée une nouvelle règle de substitution de table et charge la table de substitution de police Microsoft Windows par défaut.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// Sous Windows, le substitut par défaut de la police "Times New Roman CE" est "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Nous pouvons enregistrer le tableau sous la forme d'un document XML.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux a sa propre table de substitution.
// Il existe plusieurs polices de substitution pour "Times New Roman CE".
// Si le premier substitut, "FreeSerif" est également indisponible,
// cette règle parcourra les autres dans le tableau jusqu'à ce qu'elle en trouve une disponible.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Enregistre la table de substitution Linux sous la forme d'un document XML à l'aide d'un flux.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Voir également

* class [TableSubstitutionRule](../)
* espace de noms [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* Assemblée [Aspose.Words](../../../)

---

## Save(Stream) {#save}

Enregistre les paramètres de substitution de table actuels dans stream.

```csharp
public void Save(Stream outputStream)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| outputStream | Stream | Flux de sortie. |

### Exemples

Montre comment accéder aux tables de substitution de polices pour Windows et Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Crée une nouvelle règle de substitution de table et charge la table de substitution de police Microsoft Windows par défaut.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// Sous Windows, le substitut par défaut de la police "Times New Roman CE" est "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Nous pouvons enregistrer le tableau sous la forme d'un document XML.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux a sa propre table de substitution.
// Il existe plusieurs polices de substitution pour "Times New Roman CE".
// Si le premier substitut, "FreeSerif" est également indisponible,
// cette règle parcourra les autres dans le tableau jusqu'à ce qu'elle en trouve une disponible.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Enregistre la table de substitution Linux sous la forme d'un document XML à l'aide d'un flux.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Voir également

* class [TableSubstitutionRule](../)
* espace de noms [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* Assemblée [Aspose.Words](../../../)


