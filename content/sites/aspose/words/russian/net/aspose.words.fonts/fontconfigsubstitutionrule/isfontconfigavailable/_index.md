---
title: FontConfigSubstitutionRule.IsFontConfigAvailable
second_title: Справочник по API Aspose.Words для .NET
description: FontConfigSubstitutionRule метод. Проверить доступна ли утилита fontconfig.
type: docs
weight: 20
url: /ru/net/aspose.words.fonts/fontconfigsubstitutionrule/isfontconfigavailable/
---
## FontConfigSubstitutionRule.IsFontConfigAvailable method

Проверить, доступна ли утилита fontconfig.

```csharp
public bool IsFontConfigAvailable()
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

* class [FontConfigSubstitutionRule](../)
* пространство имен [Aspose.Words.Fonts](../../fontconfigsubstitutionrule/)
* сборка [Aspose.Words](../../../)


