---
title: Document.ExtractPages
second_title: Aspose.Words لمراجع .NET API
description: Document طريقة. إرجاع ملفDocument كائن يمثل نطاقًا محددًا من الصفحات.
type: docs
weight: 580
url: /ar/net/aspose.words/document/extractpages/
---
## Document.ExtractPages method

إرجاع ملف[`Document`](../) كائن يمثل نطاقًا محددًا من الصفحات.

```csharp
public Document ExtractPages(int index, int count)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| index | Int32 | الفهرس الصفري للصفحة الأولى المراد استخلاصها. |
| count | Int32 | عدد الصفحات المراد استخلاصها. |

### ملاحظات

يجب أن يبدو المستند الناتج مثل المستند الموجود في برنامج MS Word ، كما لو كنا قد أجرينا "طباعة صفحات محددة" - سيتم الاحتفاظ بالترقيم ، رؤوس / تذييلات وتخطيط الجداول المتقاطعة . ولكن نظرًا لوجود عدد كبير من الفروق الدقيقة ، في الظهور أثناء تقليل عدد الصفحات ، تعتبر المطابقة الكاملة للمخطط مهمة معقدة هادئة تتطلب الكثير من الجهد . اعتمادًا على تعقيد المستند ، قد تكون هناك اختلافات طفيفة في تخطيط محتويات المستند الناتج مقارنة بالمستند المصدر. أكون موضع تقدير كبير.

### أمثلة

يوضح كيفية الحصول على نطاق محدد من الصفحات من المستند.

```csharp
Document doc = new Document(MyDir + "Layout entities.docx");

doc = doc.ExtractPages(0, 2);

doc.Save(ArtifactsDir + "Document.ExtractPages.docx");
```

### أنظر أيضا

* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


