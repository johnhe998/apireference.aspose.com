---
title: Enum FontSourceType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.FontSourceType تعداد. يحدد نوع مصدر الخط.
type: docs
weight: 2810
url: /ar/net/aspose.words.fonts/fontsourcetype/
---
## FontSourceType enumeration

يحدد نوع مصدر الخط.

```csharp
public enum FontSourceType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| FontFile | `0` | أ[`FileFontSource`](../filefontsource/) الكائن الذي يمثل ملف خط واحد. |
| FontsFolder | `1` | أ[`FolderFontSource`](../folderfontsource/) الكائن الذي يمثل مجلدًا يحتوي على ملفات خط . |
| MemoryFont | `2` | أ[`MemoryFontSource`](../memoryfontsource/) كائن يمثل خطًا واحدًا في الذاكرة. |
| SystemFonts | `3` | أ[`SystemFontSource`](../systemfontsource/) يمثل كل الخطوط المثبتة على النظام. |
| FontStream | `4` | أ[`StreamFontSource`](../streamfontsource/) الكائن الذي يمثل دفقًا ببيانات الخط . |

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

* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


