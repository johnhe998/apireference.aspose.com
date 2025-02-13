---
title: FileFormatUtil.LoadFormatToSaveFormat
second_title: Aspose.Words لمراجع .NET API
description: FileFormatUtil طريقة. تحويل أLoadFormat قيمة لSaveFormat القيمة إن أمكن.
type: docs
weight: 70
url: /ar/net/aspose.words/fileformatutil/loadformattosaveformat/
---
## FileFormatUtil.LoadFormatToSaveFormat method

تحويل أ[`LoadFormat`](../../loadformat/) قيمة ل[`SaveFormat`](../../saveformat/) القيمة إن أمكن.

```csharp
public static SaveFormat LoadFormatToSaveFormat(LoadFormat loadFormat)
```

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentException | رمى عندما لا تستطيع التحويل. |

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
* enum [LoadFormat](../../loadformat/)
* class [FileFormatUtil](../)
* مساحة الاسم [Aspose.Words](../../fileformatutil/)
* المجسم [Aspose.Words](../../../)


