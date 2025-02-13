---
title: JsonDataLoadOptions.ExactDateTimeParseFormats
second_title: Aspose.Words لمراجع .NET API
description: JsonDataLoadOptions ملكية. الحصول على أو تعيين تنسيقات دقيقة لتحليل قيم JSON للتاريخ والوقت أثناء تحميل JSON. الافتراضي هو لا شيء .
type: docs
weight: 30
url: /ar/net/aspose.words.reporting/jsondataloadoptions/exactdatetimeparseformats/
---
## JsonDataLoadOptions.ExactDateTimeParseFormats property

الحصول على أو تعيين تنسيقات دقيقة لتحليل قيم JSON للتاريخ والوقت أثناء تحميل JSON. الافتراضي هو **لا شيء** .

```csharp
public IEnumerable<string> ExactDateTimeParseFormats { get; set; }
```

### ملاحظات

السلاسل المشفرة باستخدام تنسيق Microsoft® JSON للتاريخ والوقت (على سبيل المثال ، "/ التاريخ (1224043200000) /") يتم التعرف عليها دائمًا كقيم للتاريخ والوقت بغض النظر عن قيمة هذه الخاصية. تحدد الخاصية تنسيقات إضافية لاستخدامها أثناء تحليل قيم التاريخ والوقت من السلاسل بالطريقة التالية:

* متى`ExactDateTimeParseFormats` هو **لا شيء** ، يتم استخدام تنسيق ISO-8601 وجميع تنسيقات التاريخ والوقت المدعومة للثقافات الحالية والإنجليزية في الولايات المتحدة الأمريكية والإنجليزية في نيوزيلندا بالإضافة إلى ذلك في الترتيب المذكور .
* متى`ExactDateTimeParseFormats` يحتوي على سلاسل ، يتم استخدامها كتنسيقات إضافية للتاريخ والوقت باستخدام الثقافة الحالية.
* متى`ExactDateTimeParseFormats` فارغ ، لا يتم استخدام أي تنسيقات إضافية للتاريخ والوقت.

### أنظر أيضا

* class [JsonDataLoadOptions](../)
* مساحة الاسم [Aspose.Words.Reporting](../../jsondataloadoptions/)
* المجسم [Aspose.Words](../../../)


