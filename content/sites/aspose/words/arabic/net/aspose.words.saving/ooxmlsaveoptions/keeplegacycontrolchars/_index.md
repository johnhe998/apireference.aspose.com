---
title: OoxmlSaveOptions.KeepLegacyControlChars
second_title: Aspose.Words لمراجع .NET API
description: OoxmlSaveOptions ملكية. يحتفظ بالتمثيل الأصلي لأحرف التحكم القديمة.
type: docs
weight: 40
url: /ar/net/aspose.words.saving/ooxmlsaveoptions/keeplegacycontrolchars/
---
## OoxmlSaveOptions.KeepLegacyControlChars property

يحتفظ بالتمثيل الأصلي لأحرف التحكم القديمة.

```csharp
public bool KeepLegacyControlChars { get; set; }
```

### أمثلة

يوضح كيفية دعم أحرف التحكم القديمة عند التحويل إلى docx.

```csharp
Document doc = new Document(MyDir + "Legacy control character.doc");

// عندما نحفظ المستند بتنسيق OOXML ، يمكننا إنشاء كائن OoxmlSaveOptions
// ثم قم بتمريره إلى طريقة حفظ المستند لتعديل كيفية حفظ المستند.
// اضبط خاصية "KeepLegacyControlChars" على "true" للاحتفاظ بها
// الحرف القديم "ShortDateTime" أثناء الحفظ.
// اضبط خاصية "KeepLegacyControlChars" على "خطأ" لإزالتها
// الحرف القديم "ShortDateTime" من مستند الإخراج.
OoxmlSaveOptions so = new OoxmlSaveOptions(SaveFormat.Docx);
so.KeepLegacyControlChars = keepLegacyControlChars;

doc.Save(ArtifactsDir + "OoxmlSaveOptions.KeepLegacyControlChars.docx", so);

doc = new Document(ArtifactsDir + "OoxmlSaveOptions.KeepLegacyControlChars.docx");

Assert.AreEqual(keepLegacyControlChars ? "\u0013date \\@ \"MM/dd/yyyy\"\u0014\u0015\f" : "\u001e\f",
    doc.FirstSection.Body.GetText());
```

### أنظر أيضا

* class [OoxmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../ooxmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


