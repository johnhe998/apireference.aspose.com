---
title: Class FontConfigSubstitutionRule
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.FontConfigSubstitutionRule فصل. قاعدة استبدال تكوين الخط .
type: docs
weight: 2710
url: /ar/net/aspose.words.fonts/fontconfigsubstitutionrule/
---
## FontConfigSubstitutionRule class

قاعدة استبدال تكوين الخط .

```csharp
public class FontConfigSubstitutionRule : FontSubstitutionRule
```

## الخصائص

| اسم | وصف |
| --- | --- |
| override [Enabled](../../aspose.words.fonts/fontconfigsubstitutionrule/enabled/) { set; } | يحدد ما إذا كانت القاعدة ممكّنة أم لا. |

## طُرق

| اسم | وصف |
| --- | --- |
| [IsFontConfigAvailable](../../aspose.words.fonts/fontconfigsubstitutionrule/isfontconfigavailable/)() | تحقق مما إذا كانت الأداة المساعدة fontconfig متاحة أم لا. |
| [ResetCache](../../aspose.words.fonts/fontconfigsubstitutionrule/resetcache/)() | يعيد تعيين ذاكرة التخزين المؤقت لنتائج استدعاء fontconfig. |

### ملاحظات

تستخدم هذه القاعدة الأداة المساعدة fontconfig على أنظمة Linux (والأنظمة الأخرى المشابهة لـ Unix) للحصول على الاستبدال إذا كان الخط الأصلي غير متوفر.

إذا لم تكن الأداة المساعدة fontconfig متاحة ، فسيتم تجاهل هذه القاعدة.

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

* class [FontSubstitutionRule](../fontsubstitutionrule/)
* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


