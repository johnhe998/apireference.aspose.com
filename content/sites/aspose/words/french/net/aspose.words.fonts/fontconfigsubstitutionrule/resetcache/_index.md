---
title: FontConfigSubstitutionRule.ResetCache
second_title: Référence de l'API Aspose.Words pour .NET
description: FontConfigSubstitutionRule méthode. Réinitialise le cache des résultats dappel de fontconfig.
type: docs
weight: 30
url: /fr/net/aspose.words.fonts/fontconfigsubstitutionrule/resetcache/
---
## FontConfigSubstitutionRule.ResetCache method

Réinitialise le cache des résultats d'appel de fontconfig.

```csharp
public void ResetCache()
```

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

* class [FontConfigSubstitutionRule](../)
* espace de noms [Aspose.Words.Fonts](../../fontconfigsubstitutionrule/)
* Assemblée [Aspose.Words](../../../)


