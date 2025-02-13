---
title: Class XmlDataSource
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Reporting.XmlDataSource فصل. يوفر الوصول إلى بيانات ملف XML أو دفق لاستخدامه في تقرير.
type: docs
weight: 4490
url: /ar/net/aspose.words.reporting/xmldatasource/
---
## XmlDataSource class

يوفر الوصول إلى بيانات ملف XML أو دفق لاستخدامه في تقرير.

```csharp
public class XmlDataSource
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [XmlDataSource](xmldatasource/#constructor)(Stream) | إنشاء مصدر بيانات جديد ببيانات من دفق XML باستخدام الخيارات الافتراضية لتحميل بيانات XML . |
| [XmlDataSource](xmldatasource/#constructor_4)(string) | إنشاء مصدر بيانات جديد ببيانات من ملف XML باستخدام الخيارات الافتراضية لتحميل بيانات XML . |
| [XmlDataSource](xmldatasource/#constructor_2)(Stream, Stream) | إنشاء مصدر بيانات جديد ببيانات من دفق XML باستخدام دفق تعريف مخطط XML. يتم استخدام الخيارات الافتراضية لتحميل بيانات XML. |
| [XmlDataSource](xmldatasource/#constructor_1)(Stream, XmlDataLoadOptions) | إنشاء مصدر بيانات جديد ببيانات من دفق XML باستخدام الخيارات المحددة لتحميل بيانات XML . |
| [XmlDataSource](xmldatasource/#constructor_6)(string, string) | إنشاء مصدر بيانات جديد ببيانات من ملف XML باستخدام ملف تعريف مخطط XML. يتم استخدام الخيارات الافتراضية لتحميل بيانات XML. |
| [XmlDataSource](xmldatasource/#constructor_5)(string, XmlDataLoadOptions) | إنشاء مصدر بيانات جديد ببيانات من ملف XML باستخدام الخيارات المحددة لتحميل بيانات XML . |
| [XmlDataSource](xmldatasource/#constructor_3)(Stream, Stream, XmlDataLoadOptions) | إنشاء مصدر بيانات جديد ببيانات من دفق XML باستخدام دفق تعريف مخطط XML. يتم استخدام الخيارات المحددة لتحميل بيانات XML. |
| [XmlDataSource](xmldatasource/#constructor_7)(string, string, XmlDataLoadOptions) | إنشاء مصدر بيانات جديد ببيانات من ملف XML باستخدام ملف تعريف مخطط XML. يتم استخدام الخيارات المحددة لتحميل بيانات XML. |

### ملاحظات

للوصول إلى بيانات الملف أو الدفق المقابل أثناء إنشاء تقرير ، قم بتمرير مثيل من هذه الفئة كـ مصدر بيانات إلى أحد[`ReportingEngine`](../reportingengine/) إنشاء تقرير عن الحمولة الزائدة.

في مستندات النموذج ، إذا كان عنصر XML عالي المستوى يحتوي فقط على قائمة من العناصر من نفس النوع ، `XmlDataSource` يجب معاملة المثيل بنفس الطريقة كما لو كان أDataTable مثيل. خلاف ذلك ، فإن ملف`XmlDataSource` يجب معاملة المثيل بنفس الطريقة كما لو كان أDataRow مثيل. لمزيد من المعلومات ، راجع مرجع بناء الجملة (https://docs.aspose.com/display/wordsnet/Template+Syntax).

عند تمرير تعريف مخطط XML إلى مُنشئ هذه الفئة ، يتم تحديد أنواع بيانات قيم عناصر XML البسيطة والسمات وفقًا للمخطط. لذلك في مستندات النموذج ، يمكنك العمل باستخدام القيم المكتوبة بدلاً من السلاسل فقط.

عندما لا يتم تمرير تعريف مخطط XML إلى مُنشئ هذه الفئة ، يتم تحديد أنواع البيانات الخاصة بقيم عناصر XML البسيطة والسمات تلقائيًا عند تمثيل السلسلة الخاصة بها. لذلك في مستندات النموذج ، يمكنك العمل مع القيم المكتوبة في هذه الحالة أيضًا. المحرك قادر على التعرف تلقائيًا على قيم الأنواع التالية:

* Nullable
* Nullable
* Nullable
* Nullable
* String

لاحظ أنه لكي يعمل التعرف التلقائي على أنواع البيانات ، يجب تشكيل تمثيلات السلسلة لقيم عناصر XML البسيطة والسمات باستخدام إعدادات الثقافة الثابتة.

لتجاوز السلوك الافتراضي لتحميل بيانات XML ، قم بتهيئة وتمرير ملف[`XmlDataLoadOptions`](../xmldataloadoptions/) مثيل لمنشئ هذه الفئة.

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Reporting](../../aspose.words.reporting/)
* المجسم [Aspose.Words](../../)


