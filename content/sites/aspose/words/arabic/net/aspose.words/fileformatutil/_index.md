---
title: Class FileFormatUtil
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.FileFormatUtil فصل. يوفر طرقًا مساعدة للعمل مع تنسيقات الملفات  مثل اكتشاف تنسيق الملف أو تحويل امتدادات الملفات إلى / من تعدادات تنسيق الملف.
type: docs
weight: 2640
url: /ar/net/aspose.words/fileformatutil/
---
## FileFormatUtil class

يوفر طرقًا مساعدة للعمل مع تنسيقات الملفات ، مثل اكتشاف تنسيق الملف أو تحويل امتدادات الملفات إلى / من تعدادات تنسيق الملف.

```csharp
public static class FileFormatUtil
```

## طُرق

| اسم | وصف |
| --- | --- |
| static [ContentTypeToLoadFormat](../../aspose.words/fileformatutil/contenttypetoloadformat/)(string) | تحويل نوع محتوى IANA إلى قيمة تعداد تنسيق تحميل. |
| static [ContentTypeToSaveFormat](../../aspose.words/fileformatutil/contenttypetosaveformat/)(string) | تحويل نوع محتوى IANA إلى قيمة تعداد بتنسيق حفظ. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat)(Stream) | يكتشف ويعيد المعلومات المتعلقة بتنسيق مستند مخزّن في تدفق. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat_1)(string) | يكتشف ويعيد المعلومات المتعلقة بتنسيق مستند مخزن في ملف قرص. |
| static [ExtensionToSaveFormat](../../aspose.words/fileformatutil/extensiontosaveformat/)(string) | يحول امتداد اسم الملف إلى ملف[`SaveFormat`](../saveformat/) القيمة . |
| static [ImageTypeToExtension](../../aspose.words/fileformatutil/imagetypetoextension/)(ImageType) | تحويل قيمة تعداد نوع صورة Aspose.Words إلى امتداد ملف. الامتداد الذي تم إرجاعه عبارة عن سلسلة أحرف صغيرة بنقطة بادئة. |
| static [LoadFormatToExtension](../../aspose.words/fileformatutil/loadformattoextension/)(LoadFormat) | تحويل قيمة تعداد تنسيق تحميل إلى امتداد ملف. الامتداد الذي تم إرجاعه عبارة عن سلسلة أحرف صغيرة بنقطة بادئة. |
| static [LoadFormatToSaveFormat](../../aspose.words/fileformatutil/loadformattosaveformat/)(LoadFormat) | تحويل أ[`LoadFormat`](../loadformat/) قيمة ل[`SaveFormat`](../saveformat/) القيمة إن أمكن. |
| static [SaveFormatToExtension](../../aspose.words/fileformatutil/saveformattoextension/)(SaveFormat) | تحويل قيمة تم تعدادها بتنسيق حفظ إلى امتداد ملف. الامتداد الذي تم إرجاعه عبارة عن سلسلة أحرف صغيرة بنقطة بادئة. |
| static [SaveFormatToLoadFormat](../../aspose.words/fileformatutil/saveformattoloadformat/)(SaveFormat) | تحويل أ[`SaveFormat`](../saveformat/) قيمة ل[`LoadFormat`](../loadformat/) القيمة إن أمكن. |

### أمثلة

يوضح كيفية اكتشاف الترميز في ملف html.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// يتم استخدام خاصية التشفير فقط عندما نقوم بإنشاء كائن FileFormatInfo لمستند html.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


