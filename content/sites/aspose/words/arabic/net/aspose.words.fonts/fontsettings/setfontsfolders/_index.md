---
title: FontSettings.SetFontsFolders
second_title: Aspose.Words لمراجع .NET API
description: FontSettings طريقة. يضبط المجلدات حيث يبحث Aspose.Words عن خطوط TrueType عند عرض المستندات أو تضمين الخطوط.
type: docs
weight: 90
url: /ar/net/aspose.words.fonts/fontsettings/setfontsfolders/
---
## FontSettings.SetFontsFolders method

يضبط المجلدات حيث يبحث Aspose.Words عن خطوط TrueType عند عرض المستندات أو تضمين الخطوط.

```csharp
public void SetFontsFolders(string[] fontsFolders, bool recursive)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| fontsFolders | String[] | صفيف من المجلدات التي تحتوي على خطوط تروتايب. |
| recursive | Boolean | صحيح أن تفحص المجلدات المحددة بحثًا عن الخطوط بشكل متكرر. |

### ملاحظات

بشكل افتراضي ، يبحث Aspose.Words عن الخطوط المثبتة على النظام.

يؤدي تعيين هذه الخاصية إلى إعادة تعيين ذاكرة التخزين المؤقت لجميع الخطوط التي تم تحميلها مسبقًا.

### أمثلة

يوضح كيفية تعيين أدلة مصدر خطوط متعددة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");
builder.Font.Name = "Junction Light";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// لا تحتوي مصادر الخطوط لدينا على الخط الذي استخدمناه للنص في هذا المستند.
// إذا استخدمنا إعدادات الخط هذه أثناء تقديم هذا المستند ،
// Aspose.Words ستطبق خطًا احتياطيًا على النص الذي يحتوي على خط لا يمكن لـ Aspose.Words تحديد مكانه.
FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);
Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// تفتقد مصادر الخطوط الافتراضية إلى الخطين اللذين نستخدمهما في هذا المستند.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

// استخدم طريقة "SetFontsFolders" لإنشاء مصدر خط من كل دليل خط نقوم بتمريره باعتباره الوسيطة الأولى.
// تمرير "خطأ" كوسيطة "متكررة" لتضمين الخطوط من كافة ملفات الخطوط الموجودة في الدلائل
// أننا نمرر في الوسيطة الأولى ، لكن لا نقوم بتضمين أي خطوط من أي من المجلدات الفرعية للمجلدات.
// قم بتمرير "true" باعتباره الوسيطة "العودية" لتضمين جميع ملفات الخطوط في الدلائل التي نقوم بتمريرها
// في الوسيطة الأولى ، بالإضافة إلى جميع الخطوط في الدلائل الفرعية الخاصة بهم.
FontSettings.DefaultInstance.SetFontsFolders(new[] {FontsDir + "/Amethysta", FontsDir + "/Junction"},
    recursive);

FontSourceBase[] newFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(2, newFontSources.Length);
Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.AreEqual(1, newFontSources[0].GetAvailableFonts().Count);
Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// لا يحتوي مجلد "Junction" نفسه على ملفات خطوط ، ولكنه يحتوي على مجلدات فرعية تعمل.
if (recursive)
{
    Assert.AreEqual(6, newFontSources[1].GetAvailableFonts().Count);
    Assert.True(newFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));
}
else
{
    Assert.AreEqual(0, newFontSources[1].GetAvailableFonts().Count);
}

doc.Save(ArtifactsDir + "FontSettings.SetFontsFolders.pdf");

// استعادة مصادر الخط الأصلية.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### أنظر أيضا

* class [FontSettings](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontsettings/)
* المجسم [Aspose.Words](../../../)


