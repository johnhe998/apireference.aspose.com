---
title: FontConfigSubstitutionRule.ResetCache
second_title: Aspose.Words لمراجع .NET API
description: FontConfigSubstitutionRule طريقة. يعيد تعيين ذاكرة التخزين المؤقت لنتائج استدعاء fontconfig.
type: docs
weight: 30
url: /ar/net/aspose.words.fonts/fontconfigsubstitutionrule/resetcache/
---
## FontConfigSubstitutionRule.ResetCache method

يعيد تعيين ذاكرة التخزين المؤقت لنتائج استدعاء fontconfig.

```csharp
public void ResetCache()
```

### أمثلة

يعرض استبدال تكوين الخط المعتمد على نظام التشغيل.

```csharp
FontSettings fontSettings = new FontSettings();
FontConfigSubstitutionRule fontConfigSubstitution =
    fontSettings.SubstitutionSettings.FontConfigSubstitution;

bool isWindows = new[] {PlatformID.Win32NT, PlatformID.Win32S, PlatformID.Win32Windows, PlatformID.WinCE}
    .Any(p => Environment.OSVersion.Platform == p);

// يعمل كائن FontConfigSubstitutionRule بشكل مختلف على أنظمة تشغيل Windows / غير أنظمة تشغيل Windows.
// في Windows ، إنه غير متوفر.
if (isWindows)
{
    Assert.False(fontConfigSubstitution.Enabled);
    Assert.False(fontConfigSubstitution.IsFontConfigAvailable());
}

bool isLinuxOrMac =
    new[] {PlatformID.Unix, PlatformID.MacOSX}.Any(p => Environment.OSVersion.Platform == p);

// في Linux / Mac ، سنتمكن من الوصول إليه ، وسنكون قادرين على إجراء العمليات.
if (isLinuxOrMac)
{
    Assert.True(fontConfigSubstitution.Enabled);
    Assert.True(fontConfigSubstitution.IsFontConfigAvailable());

    fontConfigSubstitution.ResetCache();
}
```

### أنظر أيضا

* class [FontConfigSubstitutionRule](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontconfigsubstitutionrule/)
* المجسم [Aspose.Words](../../../)


