---
title: License.License
second_title: Aspose.Words لمراجع .NET API
description: License البناء. تهيئة مثيل جديد لهذه الفئة.
type: docs
weight: 10
url: /ar/net/aspose.words/license/license/
---
## License constructor

تهيئة مثيل جديد لهذه الفئة.

```csharp
public License()
```

### أمثلة

يوضح كيفية تهيئة ترخيص لـ Aspose.Words باستخدام ملف ترخيص في نظام الملفات المحلي.

```csharp
// قم بتعيين ترخيص منتج Aspose.Words الخاص بنا عن طريق تمرير اسم ملف نظام الملفات المحلي لملف ترخيص صالح.
string licenseFileName = Path.Combine(LicenseDir, "Aspose.Words.NET.lic");

License license = new License();
license.SetLicense(licenseFileName);

// أنشئ نسخة من ملف الترخيص الخاص بنا في مجلد الثنائيات لتطبيقنا.
string licenseCopyFileName = Path.Combine(AssemblyDir, "Aspose.Words.NET.lic");
File.Copy(licenseFileName, licenseCopyFileName);

// إذا مررنا اسم ملف بدون مسار ،
// سيبحث SetLicense في العديد من مواقع نظام الملفات المحلي لهذا الملف.
// سيكون أحد هذه المواقع هو مجلد "bin" ، الذي يحتوي على نسخة من ملف الترخيص الخاص بنا.
license.SetLicense("Aspose.Words.NET.lic");
```

### أنظر أيضا

* class [License](../)
* مساحة الاسم [Aspose.Words](../../license/)
* المجسم [Aspose.Words](../../../)


