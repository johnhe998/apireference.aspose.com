---
title: Enum ReportBuildOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Reporting.ReportBuildOptions تعداد. يحدد الخيارات التي تتحكم في سلوكReportingEngine أثناء إنشاء تقرير.
type: docs
weight: 4460
url: /ar/net/aspose.words.reporting/reportbuildoptions/
---
## ReportBuildOptions enumeration

يحدد الخيارات التي تتحكم في سلوك[`ReportingEngine`](../reportingengine/) أثناء إنشاء تقرير.

```csharp
[Flags]
public enum ReportBuildOptions
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | تحديد الخيارات الافتراضية . |
| AllowMissingMembers | `1` | تحديد أن أعضاء الكائن المفقود يجب أن يعاملوا على أنهم قيم خالية من قبل المحرك. يؤثر هذا الخيار على الوصول فقط إلى أعضاء الكائن وطرق الامتداد المثيل (أي ، غير ثابت). إذا لم يتم تعيين خيار هذا ، فسيقوم المحرك بإصدار استثناء عندما يواجه عضو كائن مفقود. |
| RemoveEmptyParagraphs | `2` | يحدد أنه يجب على المحرك إزالة الفقرات التي تصبح فارغة بعد إزالة علامات بناء الجملة أو استبدالها بقيم فارغة . |
| InlineErrorMessages | `4` | تحديد أنه يجب على المحرك تضمين رسائل خطأ بنية القالب في مستندات الإخراج. إذا لم يتم تعيين هذا الخيار ، فسيقوم المحرك بإصدار استثناء عند مواجهة خطأ في بناء الجملة. |
| UseLegacyHeaderFooterVisiting | `8` | يحدد أن المحرك يجب أن يزور العقد الفرعية للقسم (الرؤوس والتذييلات والنصوص) بترتيب متوافق مع إصدارات Aspose.Words السابقة 21.9. |
| RespectJpegExifOrientation | `10` | يحدد أن المحرك يجب أن يستخدم قيم اتجاه الصورة EXIF ​​لتدوير الصور المدرجة JPEG . |

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Reporting](../../aspose.words.reporting/)
* المجسم [Aspose.Words](../../)


