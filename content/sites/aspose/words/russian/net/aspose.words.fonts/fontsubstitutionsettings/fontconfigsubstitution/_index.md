---
title: FontSubstitutionSettings.FontConfigSubstitution
second_title: Справочник по API Aspose.Words для .NET
description: FontSubstitutionSettings свойство. Настройки связанные с правилом подстановки конфигурации шрифта.
type: docs
weight: 20
url: /ru/net/aspose.words.fonts/fontsubstitutionsettings/fontconfigsubstitution/
---
## FontSubstitutionSettings.FontConfigSubstitution property

Настройки, связанные с правилом подстановки конфигурации шрифта.

```csharp
public FontConfigSubstitutionRule FontConfigSubstitution { get; }
```

### Примеры

Показывает подстановку конфигурации шрифта в зависимости от операционной системы.

```csharp
FontSettings fontSettings = new FontSettings();
FontConfigSubstitutionRule fontConfigSubstitution =
    fontSettings.SubstitutionSettings.FontConfigSubstitution;

bool isWindows = new[] {PlatformID.Win32NT, PlatformID.Win32S, PlatformID.Win32Windows, PlatformID.WinCE}
    .Any(p => Environment.OSVersion.Platform == p);

// Объект FontConfigSubstitutionRule работает по-разному на платформах Windows/отличных от Windows.
// В Windows он недоступен.
if (isWindows)
{
    Assert.False(fontConfigSubstitution.Enabled);
    Assert.False(fontConfigSubstitution.IsFontConfigAvailable());
}

bool isLinuxOrMac =
    new[] {PlatformID.Unix, PlatformID.MacOSX}.Any(p => Environment.OSVersion.Platform == p);

// В Linux/Mac у нас будет к нему доступ, и мы сможем выполнять операции.
if (isLinuxOrMac)
{
    Assert.True(fontConfigSubstitution.Enabled);
    Assert.True(fontConfigSubstitution.IsFontConfigAvailable());

    fontConfigSubstitution.ResetCache();
}
```

### Смотрите также

* class [FontConfigSubstitutionRule](../../fontconfigsubstitutionrule/)
* class [FontSubstitutionSettings](../)
* пространство имен [Aspose.Words.Fonts](../../fontsubstitutionsettings/)
* сборка [Aspose.Words](../../../)


