---
title: FontSettings.GetFontsSources
second_title: Aspose.Words لمراجع .NET API
description: FontSettings طريقة. يحصل على نسخة من المصفوفة التي تحتوي على قائمة المصادر حيث يبحث Aspose.Words عن خطوط TrueType .
type: docs
weight: 50
url: /ar/net/aspose.words.fonts/fontsettings/getfontssources/
---
## FontSettings.GetFontsSources method

يحصل على نسخة من المصفوفة التي تحتوي على قائمة المصادر حيث يبحث Aspose.Words عن خطوط TrueType .

```csharp
public FontSourceBase[] GetFontsSources()
```

### قيمة الإرجاع

نسخة من مصادر الخط الحالية.

### ملاحظات

القيمة التي تم إرجاعها هي نسخة من البيانات التي يستخدمها Aspose.Words. إذا قمت بتغيير الإدخالات في المصفوفة التي تم إرجاعها ، فلن يكون لها أي تأثير على عرض المستند. لتحديد مصادر خط جديدة استخدم ملف[`SetFontsSources`](../setfontssources/) طريقة.

### أمثلة

يوضح كيفية إضافة مصدر خط إلى مصادر الخطوط الموجودة لدينا.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");
builder.Font.Name = "Junction Light";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);

Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// يفتقد مصدر الخط الافتراضي إلى اثنين من الخطوط التي نستخدمها في وثيقتنا.
// عندما نحفظ هذا المستند ، ستطبق Aspose.Words الخطوط الاحتياطية على جميع النصوص المنسقة بخطوط لا يمكن الوصول إليها.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

// إنشاء مصدر خط من مجلد يحتوي على خطوط.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);

// قم بتطبيق مجموعة جديدة من مصادر الخطوط التي تحتوي على مصادر الخطوط الأصلية ، بالإضافة إلى الخطوط المخصصة لدينا.
FontSourceBase[] updatedFontSources = {originalFontSources[0], folderFontSource};
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);

// تحقق من أن Aspose.Words حق الوصول إلى جميع الخطوط المطلوبة قبل تقديم المستند إلى PDF.
updatedFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.True(updatedFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(updatedFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.True(updatedFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

doc.Save(ArtifactsDir + "FontSettings.AddFontSource.pdf");

// استعادة مصادر الخط الأصلية.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### أنظر أيضا

* class [FontSourceBase](../../fontsourcebase/)
* class [FontSettings](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontsettings/)
* المجسم [Aspose.Words](../../../)


