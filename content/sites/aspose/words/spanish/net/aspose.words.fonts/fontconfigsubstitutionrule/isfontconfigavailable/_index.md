---
title: FontConfigSubstitutionRule.IsFontConfigAvailable
second_title: Referencia de API de Aspose.Words para .NET
description: FontConfigSubstitutionRule método. Compruebe si la utilidad fontconfig está disponible o no.
type: docs
weight: 20
url: /es/net/aspose.words.fonts/fontconfigsubstitutionrule/isfontconfigavailable/
---
## FontConfigSubstitutionRule.IsFontConfigAvailable method

Compruebe si la utilidad fontconfig está disponible o no.

```csharp
public bool IsFontConfigAvailable()
```

### Ejemplos

Muestra la sustitución de configuración de fuente dependiente del sistema operativo.

```csharp
FontSettings fontSettings = new FontSettings();
FontConfigSubstitutionRule fontConfigSubstitution =
    fontSettings.SubstitutionSettings.FontConfigSubstitution;

bool isWindows = new[] {PlatformID.Win32NT, PlatformID.Win32S, PlatformID.Win32Windows, PlatformID.WinCE}
    .Any(p => Environment.OSVersion.Platform == p);

// El objeto FontConfigSubstitutionRule funciona de manera diferente en plataformas Windows y no Windows.
// En Windows, no está disponible.
if (isWindows)
{
    Assert.False(fontConfigSubstitution.Enabled);
    Assert.False(fontConfigSubstitution.IsFontConfigAvailable());
}

bool isLinuxOrMac =
    new[] {PlatformID.Unix, PlatformID.MacOSX}.Any(p => Environment.OSVersion.Platform == p);

// En Linux/Mac, tendremos acceso a él y podremos realizar operaciones.
if (isLinuxOrMac)
{
    Assert.True(fontConfigSubstitution.Enabled);
    Assert.True(fontConfigSubstitution.IsFontConfigAvailable());

    fontConfigSubstitution.ResetCache();
}
```

### Ver también

* class [FontConfigSubstitutionRule](../)
* espacio de nombres [Aspose.Words.Fonts](../../fontconfigsubstitutionrule/)
* asamblea [Aspose.Words](../../../)


