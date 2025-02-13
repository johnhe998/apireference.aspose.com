---
title: FileFormatUtil.SaveFormatToLoadFormat
second_title: Aspose.Words لمراجع .NET API
description: FileFormatUtil طريقة. تحويل أSaveFormat قيمة لLoadFormat القيمة إن أمكن.
type: docs
weight: 90
url: /ar/net/aspose.words/fileformatutil/saveformattoloadformat/
---
## FileFormatUtil.SaveFormatToLoadFormat method

تحويل أ[`SaveFormat`](../../saveformat/) قيمة ل[`LoadFormat`](../../loadformat/) القيمة إن أمكن.

```csharp
public static LoadFormat SaveFormatToLoadFormat(SaveFormat saveFormat)
```

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentException | رمى عندما لا تستطيع التحويل. |

### أمثلة

يوضح كيفية تحويل تنسيق الحفظ إلى تنسيق التحميل المقابل له.

```csharp
Assert.AreEqual(LoadFormat.Html, FileFormatUtil.SaveFormatToLoadFormat(SaveFormat.Html));

// يمكن حفظ المستندات في بعض أنواع الملفات ، ولكن لا يتم تحميلها من استخدام Aspose.Words.
// إذا حاولنا تحويل تنسيق حفظ من هذا النوع إلى تنسيق تحميل ، فسيتم طرح استثناء.
Assert.Throws<ArgumentException>(() => FileFormatUtil.SaveFormatToLoadFormat(SaveFormat.Jpeg));
```

### أنظر أيضا

* enum [LoadFormat](../../loadformat/)
* enum [SaveFormat](../../saveformat/)
* class [FileFormatUtil](../)
* مساحة الاسم [Aspose.Words](../../fileformatutil/)
* المجسم [Aspose.Words](../../../)


