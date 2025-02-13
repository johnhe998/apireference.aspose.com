---
title: تحقق من تأثير النص DrawingML
linktitle: تحقق من تأثير النص DrawingML
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: في هذا البرنامج التعليمي ، تعرف على كيفية التحقق من تأثيرات نص DrawingML في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/check-drawingml-text-effect/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية التحقق من تأثيرات نص DrawingML في مستند Word باستخدام Aspose.Words Library for .NET. يتيح لك التحقق من تأثيرات نص DrawingML تحديد ما إذا تم تطبيق تأثير معين على جزء من النص. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك
- مستند Word يحتوي على تأثيرات نصية DrawingML

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وتحقق من تأثيرات النص
بعد ذلك ، سنقوم بتحميل مستند Word والوصول إلى مجموعة عمليات التشغيل (تسلسل الأحرف) في الفقرة الأولى من نص المستند. بعد ذلك ، سوف نتحقق مما إذا تم تطبيق أي تأثيرات نصية معينة لـ DrawingML على خط التشغيل الأول.

```csharp
// قم بتحميل المستند
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// تحقق من تأثيرات النص DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### عينة من التعليمات البرمجية المصدر للتحقق من تأثير DMLText باستخدام Aspose.Words for .NET 

```csharp

//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// قد يكون للتشغيل الواحد عدة تأثيرات نصية Dml مطبقة.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية التحقق من تأثيرات نص DrawingML في مستند Word باستخدام Aspose.Words for .NET. يتيح لك التحقق من تأثيرات نص DrawingML تحديد أجزاء النص التي تم تطبيق تأثيرات معينة عليها. لا تتردد في استخدام هذه الميزة لمعالجة وتحليل تأثيرات النص في مستندات Word الخاصة بك.

### التعليمات

#### س: كيف يمكنني الوصول إلى تأثيرات نص DrawingML في مستند Word باستخدام Aspose.Words؟

ج: باستخدام Aspose.Words ، يمكنك الوصول إلى تأثيرات نصية DrawingML في مستند Word باستخدام واجهة برمجة التطبيقات المتوفرة. يمكنك تصفح عناصر النص والتحقق من خصائص معينة لتأثيرات النص ، مثل اللون والحجم وما إلى ذلك.

#### س: ما هي أنواع تأثيرات النص DrawingML المستخدمة بشكل شائع في مستندات Word؟

ج: تشمل الأنواع الشائعة الاستخدام من تأثيرات نص DrawingML في مستندات Word الظلال والانعكاسات والتوهجات والتدرجات اللونية وما إلى ذلك. يمكن تطبيق هذه التأثيرات لتحسين مظهر النص وتنسيقه.

#### س: كيف يمكنني التحقق من لون تأثير نص DrawingML في مستند Word؟

ج: للتحقق من لون تأثير نص DrawingML في مستند Word ، يمكنك استخدام الطرق التي يوفرها Aspose.Words للوصول إلى خصائص لون تأثير النص. بهذه الطريقة يمكنك الحصول على اللون المستخدم لتأثير النص المحدد.

#### س: هل من الممكن التحقق من تأثيرات النص في مستندات Word التي تحتوي على أقسام متعددة؟

ج: نعم ، يسمح Aspose.Words بفحص تأثيرات النص في مستندات Word التي تحتوي على أقسام متعددة. يمكنك التنقل عبر كل قسم من المستند والوصول إلى تأثيرات النص لكل قسم على حدة.

#### س: كيف يمكنني التحقق من عتامة تأثير نص DrawingML في مستند Word؟

ج: للتحقق من عتامة تأثير نص DrawingML في مستند Word ، يمكنك استخدام الطرق التي يوفرها Aspose.Words للوصول إلى خصائص عتامة تأثير النص. سيسمح لك هذا بالحصول على قيمة العتامة المطبقة على تأثير النص المحدد.