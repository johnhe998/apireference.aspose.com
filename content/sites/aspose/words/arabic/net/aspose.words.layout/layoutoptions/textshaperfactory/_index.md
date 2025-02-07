---
title: LayoutOptions.TextShaperFactory
second_title: Aspose.Words لمراجع .NET API
description: LayoutOptions ملكية. يحصل أو يحددITextShaperFactory التنفيذ المستخدم لميزات عرض الطباعة المتقدمة.
type: docs
weight: 90
url: /ar/net/aspose.words.layout/layoutoptions/textshaperfactory/
---
## LayoutOptions.TextShaperFactory property

يحصل أو يحدد[`ITextShaperFactory`](../../../aspose.words.shaping/itextshaperfactory/) التنفيذ المستخدم لميزات عرض الطباعة المتقدمة.

```csharp
public ITextShaperFactory TextShaperFactory { get; set; }
```

### أمثلة

يوضح كيفية دعم ميزات OpenType باستخدام محرك تشكيل النص HarfBuzz.

```csharp
Document doc = new Document(MyDir + "OpenType text shaping.docx");

// Aspose.Words يمكن أن تستخدم كائنات تشكيل النص المقدمة خارجيًا ،
// التي تمثل الخطوط وتحسب معلومات تشكيل النص.
// يعد مصنع تشكيل النص ضروريًا للمستندات التي تستخدم خطوطًا متعددة.
// عند ضبط المصنع لمشكل النص ، يستخدم التخطيط ميزات OpenType.
// إرجاع خاصية مثيل كائن BasicTextShaperCache ثابت التفاف HarfBuzzTextShaperFactory.
doc.LayoutOptions.TextShaperFactory = HarfBuzzTextShaperFactory.Instance;

// حاليًا ، يتم تنفيذ تشكيل النص عند التصدير إلى تنسيقات PDF أو XPS.
doc.Save(ArtifactsDir + "Document.OpenType.pdf");
```

### أنظر أيضا

* interface [ITextShaperFactory](../../../aspose.words.shaping/itextshaperfactory/)
* class [LayoutOptions](../)
* مساحة الاسم [Aspose.Words.Layout](../../layoutoptions/)
* المجسم [Aspose.Words](../../../)


