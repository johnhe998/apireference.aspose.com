---
title: FileFormatUtil.SaveFormatToExtension
second_title: Aspose.Words لمراجع .NET API
description: FileFormatUtil طريقة. تحويل قيمة تم تعدادها بتنسيق حفظ إلى امتداد ملف. الامتداد الذي تم إرجاعه عبارة عن سلسلة أحرف صغيرة بنقطة بادئة.
type: docs
weight: 80
url: /ar/net/aspose.words/fileformatutil/saveformattoextension/
---
## FileFormatUtil.SaveFormatToExtension method

تحويل قيمة تم تعدادها بتنسيق حفظ إلى امتداد ملف. الامتداد الذي تم إرجاعه عبارة عن سلسلة أحرف صغيرة بنقطة بادئة.

```csharp
public static string SaveFormatToExtension(SaveFormat saveFormat)
```

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentException | رمى عندما لا تستطيع التحويل. |

### ملاحظات

الWordML يتم تحويل القيمة إلى ".wml".

الFlatOpc يتم تحويل القيمة إلى ".fopc".

### أمثلة

يوضح كيفية استخدام أساليب FileFormatUtil لاكتشاف تنسيق المستند.

```csharp
// قم بتحميل مستند من ملف يفتقد إلى امتداد الملف ، ثم اكتشف تنسيق الملف الخاص به.
using (FileStream docStream = File.OpenRead(MyDir + "Word document with missing file extension"))
{
    FileFormatInfo info = FileFormatUtil.DetectFileFormat(docStream);
    LoadFormat loadFormat = info.LoadFormat;

    Assert.AreEqual(LoadFormat.Doc, loadFormat);

    // فيما يلي طريقتان لتحويل LoadFormat إلى SaveFormat المقابل له.
    // 1 - احصل على سلسلة امتداد الملف لـ LoadFormat ، ثم احصل على تنسيق SaveFormat المقابل من تلك السلسلة:
    string fileExtension = FileFormatUtil.LoadFormatToExtension(loadFormat);
    SaveFormat saveFormat = FileFormatUtil.ExtensionToSaveFormat(fileExtension);

    // 2 - تحويل LoadFormat مباشرة إلى SaveFormat الخاص به:
    saveFormat = FileFormatUtil.LoadFormatToSaveFormat(loadFormat);

    // قم بتحميل مستند من الدفق ، ثم احفظه في امتداد الملف المكتشف تلقائيًا.
    Document doc = new Document(docStream);

    Assert.AreEqual(".doc", FileFormatUtil.SaveFormatToExtension(saveFormat));

    doc.Save(ArtifactsDir + "File.SaveToDetectedFileFormat" + FileFormatUtil.SaveFormatToExtension(saveFormat));
}
```

### أنظر أيضا

* enum [SaveFormat](../../saveformat/)
* class [FileFormatUtil](../)
* مساحة الاسم [Aspose.Words](../../fileformatutil/)
* المجسم [Aspose.Words](../../../)


