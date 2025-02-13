---
title: TableSubstitutionRule.Save
second_title: Aspose.Words لمراجع .NET API
description: TableSubstitutionRule طريقة. يحفظ إعدادات الاستبدال الحالية للجدول في ملف.
type: docs
weight: 70
url: /ar/net/aspose.words.fonts/tablesubstitutionrule/save/
---
## Save(string) {#save_1}

يحفظ إعدادات الاستبدال الحالية للجدول في ملف.

```csharp
public void Save(string fileName)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| fileName | String | ضع اسم الملف. |

### أمثلة

يوضح كيفية الوصول إلى جداول استبدال الخطوط لنظامي التشغيل Windows و Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// قم بإنشاء قاعدة استبدال جديدة للجدول وقم بتحميل جدول استبدال خطوط Microsoft Windows الافتراضي.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// في Windows ، البديل الافتراضي لخط "Times New Roman CE" هو "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// يمكننا حفظ الجدول في شكل وثيقة XML.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// لينكس لديه جدول الاستبدال الخاص به.
// هناك عدة خطوط بديلة لـ "Times New Roman CE".
// إذا كان البديل الأول "FreeSerif" غير متوفر أيضًا ،
// ستنتقل هذه القاعدة بين الآخرين في المصفوفة حتى تجد قاعدة متاحة.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// احفظ جدول استبدال Linux في شكل مستند XML باستخدام التدفق.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### أنظر أيضا

* class [TableSubstitutionRule](../)
* مساحة الاسم [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* المجسم [Aspose.Words](../../../)

---

## Save(Stream) {#save}

يحفظ إعدادات استبدال الجدول الحالية للدفق.

```csharp
public void Save(Stream outputStream)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| outputStream | Stream | تيار الإخراج. |

### أمثلة

يوضح كيفية الوصول إلى جداول استبدال الخطوط لنظامي التشغيل Windows و Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// قم بإنشاء قاعدة استبدال جديدة للجدول وقم بتحميل جدول استبدال خطوط Microsoft Windows الافتراضي.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// في Windows ، البديل الافتراضي لخط "Times New Roman CE" هو "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// يمكننا حفظ الجدول في شكل وثيقة XML.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// لينكس لديه جدول الاستبدال الخاص به.
// هناك عدة خطوط بديلة لـ "Times New Roman CE".
// إذا كان البديل الأول "FreeSerif" غير متوفر أيضًا ،
// ستنتقل هذه القاعدة بين الآخرين في المصفوفة حتى تجد قاعدة متاحة.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// احفظ جدول استبدال Linux في شكل مستند XML باستخدام التدفق.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### أنظر أيضا

* class [TableSubstitutionRule](../)
* مساحة الاسم [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* المجسم [Aspose.Words](../../../)


