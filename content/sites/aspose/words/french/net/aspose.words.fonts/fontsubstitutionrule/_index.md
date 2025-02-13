---
title: Class FontSubstitutionRule
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fonts.FontSubstitutionRule classe. Il sagit dune classe de base abstraite pour la règle de substitution de police.
type: docs
weight: 2820
url: /fr/net/aspose.words.fonts/fontsubstitutionrule/
---
## FontSubstitutionRule class

Il s'agit d'une classe de base abstraite pour la règle de substitution de police.

```csharp
public abstract class FontSubstitutionRule
```

## Propriétés

| Nom | La description |
| --- | --- |
| virtual [Enabled](../../aspose.words.fonts/fontsubstitutionrule/enabled/) { get; set; } | Spécifie si la règle est activée ou non. |

### Exemples

Affiche la substitution de la configuration des polices en fonction du système d'exploitation.

```csharp
FontSettings fontSettings = new FontSettings();
FontConfigSubstitutionRule fontConfigSubstitution =
    fontSettings.SubstitutionSettings.FontConfigSubstitution;

bool isWindows = new[] {PlatformID.Win32NT, PlatformID.Win32S, PlatformID.Win32Windows, PlatformID.WinCE}
    .Any(p => Environment.OSVersion.Platform == p);

// L'objet FontConfigSubstitutionRule fonctionne différemment sur les plates-formes Windows/non Windows.
// Sous Windows, il n'est pas disponible.
if (isWindows)
{
    Assert.False(fontConfigSubstitution.Enabled);
    Assert.False(fontConfigSubstitution.IsFontConfigAvailable());
}

bool isLinuxOrMac =
    new[] {PlatformID.Unix, PlatformID.MacOSX}.Any(p => Environment.OSVersion.Platform == p);

// Sous Linux/Mac, nous y aurons accès, et pourrons effectuer des opérations.
if (isLinuxOrMac)
{
    Assert.True(fontConfigSubstitution.Enabled);
    Assert.True(fontConfigSubstitution.IsFontConfigAvailable());

    fontConfigSubstitution.ResetCache();
}
```

### Voir également

* espace de noms [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Assemblée [Aspose.Words](../../)


