---
title: FileFontSource.FilePath
second_title: Aspose.Words لمراجع .NET API
description: FileFontSource ملكية. المسار إلى ملف الخط.
type: docs
weight: 30
url: /ar/net/aspose.words.fonts/filefontsource/filepath/
---
## FileFontSource.FilePath property

المسار إلى ملف الخط.

```csharp
public string FilePath { get; }
```

### أمثلة

يوضح كيفية استخدام ملف خط في نظام الملفات المحلي كمصدر للخط.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### أنظر أيضا

* class [FileFontSource](../)
* مساحة الاسم [Aspose.Words.Fonts](../../filefontsource/)
* المجسم [Aspose.Words](../../../)


