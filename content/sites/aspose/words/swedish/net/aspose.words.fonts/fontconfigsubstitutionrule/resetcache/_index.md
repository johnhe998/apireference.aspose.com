---
title: FontConfigSubstitutionRule.ResetCache
second_title: Aspose.Words för .NET API Referens
description: FontConfigSubstitutionRule metod. Återställer cachen för fontconfiganropsresultat.
type: docs
weight: 30
url: /sv/net/aspose.words.fonts/fontconfigsubstitutionrule/resetcache/
---
## FontConfigSubstitutionRule.ResetCache method

Återställer cachen för fontconfig-anropsresultat.

```csharp
public void ResetCache()
```

### Exempel

Visar operativsystemberoende teckensnittskonfigurationsersättning.

```csharp
FontSettings fontSettings = new FontSettings();
FontConfigSubstitutionRule fontConfigSubstitution =
    fontSettings.SubstitutionSettings.FontConfigSubstitution;

bool isWindows = new[] {PlatformID.Win32NT, PlatformID.Win32S, PlatformID.Win32Windows, PlatformID.WinCE}
    .Any(p => Environment.OSVersion.Platform == p);

// FontConfigSubstitutionRule-objektet fungerar annorlunda på Windows/icke-Windows-plattformar.
// På Windows är det inte tillgängligt.
if (isWindows)
{
    Assert.False(fontConfigSubstitution.Enabled);
    Assert.False(fontConfigSubstitution.IsFontConfigAvailable());
}

bool isLinuxOrMac =
    new[] {PlatformID.Unix, PlatformID.MacOSX}.Any(p => Environment.OSVersion.Platform == p);

// På Linux/Mac kommer vi att ha tillgång till det och kommer att kunna utföra operationer.
if (isLinuxOrMac)
{
    Assert.True(fontConfigSubstitution.Enabled);
    Assert.True(fontConfigSubstitution.IsFontConfigAvailable());

    fontConfigSubstitution.ResetCache();
}
```

### Se även

* class [FontConfigSubstitutionRule](../)
* namnutrymme [Aspose.Words.Fonts](../../fontconfigsubstitutionrule/)
* hopsättning [Aspose.Words](../../../)


