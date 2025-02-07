---
title: FolderFontSource.FolderFontSource
second_title: Aspose.Words لمراجع .NET API
description: FolderFontSource البناء. Ctor.
type: docs
weight: 10
url: /ar/net/aspose.words.fonts/folderfontsource/folderfontsource/
---
## FolderFontSource(string, bool) {#constructor}

Ctor.

```csharp
public FolderFontSource(string folderPath, bool scanSubfolders)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| folderPath | String | مسار المجلد. |
| scanSubfolders | Boolean | يحدد ما إذا كان سيتم فحص المجلدات الفرعية أم لا. |

### أمثلة

يوضح كيفية استخدام مجلد نظام محلي يحتوي على خطوط كمصدر للخط.

```csharp
// إنشاء مصدر خط من مجلد يحتوي على ملفات الخطوط.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### أنظر أيضا

* class [FolderFontSource](../)
* مساحة الاسم [Aspose.Words.Fonts](../../folderfontsource/)
* المجسم [Aspose.Words](../../../)

---

## FolderFontSource(string, bool, int) {#constructor_1}

Ctor.

```csharp
public FolderFontSource(string folderPath, bool scanSubfolders, int priority)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| folderPath | String | مسار المجلد. |
| scanSubfolders | Boolean | يحدد ما إذا كان سيتم فحص المجلدات الفرعية أم لا. |
| priority | Int32 | أولوية مصدر الخط. انظر[`Priority`](../../fontsourcebase/priority/) وصف الخاصية لمزيد من المعلومات. |

### أمثلة

يوضح كيفية استخدام مجلد نظام محلي يحتوي على خطوط كمصدر للخط.

```csharp
// إنشاء مصدر خط من مجلد يحتوي على ملفات الخطوط.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### أنظر أيضا

* class [FolderFontSource](../)
* مساحة الاسم [Aspose.Words.Fonts](../../folderfontsource/)
* المجسم [Aspose.Words](../../../)


