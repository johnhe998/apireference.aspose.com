---
title: حدد الخط الافتراضي عند التقديم
linktitle: حدد الخط الافتراضي عند التقديم
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل تفصيلي خطوة بخطوة لتحديد الخط الافتراضي عند تقديم مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/specify-default-font-when-rendering/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتحديد الخط الافتراضي عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد خط افتراضي لاستخدامه عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند للعرض
 بعد ذلك ، تحتاج إلى تحميل المستند لتقديمه باستخدام امتداد`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تعيين الخط الافتراضي
 يمكنك الآن تحديد الخط الافتراضي لاستخدامه عند التقديم عن طريق إنشاء مثيل لملف`FontSettings` الطبقة ووضع`DefaultFontName`ممتلكات`DefaultFontSubstitution` يعترض على`DefaultFontSubstitution` هدف`SubstitutionSettings` ل`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## الخطوة 4: احفظ المستند المقدم
 أخيرًا ، يمكنك حفظ المستند الذي تم تقديمه في ملف باستخدام امتداد`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### عينة من التعليمات البرمجية المصدر لـ Specify Default Font عند العرض باستخدام Aspose.Words for .NET 

```csharp
//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// إذا كان الخط الافتراضي المحدد هنا لا يمكن العثور عليه أثناء التقديم ، فحينئذٍ
// يتم استخدام أقرب خط على الجهاز بدلاً من ذلك.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحديد الخط الافتراضي عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تعيين خط افتراضي لاستخدامه عند عرض المستندات الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات باستخدام الخطوط في مستنداتك. باستخدام هذه المعرفة ، يمكنك التحكم في عرض مستنداتك وتخصيصه وفقًا لاحتياجاتك الخاصة.

### التعليمات

#### س: كيف يمكنني تحديد خط افتراضي عند التحويل إلى PDF في Aspose.Words؟

 ج: لتحديد خط افتراضي عند التحويل إلى PDF في Aspose.Words ، يمكنك استخدام`PdfOptions`فئة وضبط`DefaultFontName` الخاصية لاسم الخط المطلوب.

#### س: ماذا لو لم يكن الخط الافتراضي متاحًا عند التحويل إلى PDF؟

ج: إذا لم يكن الخط الافتراضي المحدد متاحًا عند التحويل إلى PDF ، فستستخدم Aspose.Words خطًا بديلاً لعرض النص في المستند المحول. قد يتسبب هذا في اختلاف بسيط في المظهر من الخط الأصلي.

#### س: هل يمكنني تحديد خط افتراضي لتنسيقات الإخراج الأخرى ، مثل DOCX أو HTML؟

ج: نعم ، يمكنك تحديد خط افتراضي لتنسيقات الإخراج الأخرى مثل DOCX أو HTML باستخدام خيارات التحويل المناسبة وتعيين الخاصية المقابلة لكل تنسيق.

#### س: كيف يمكنني التحقق من الخط الافتراضي المحدد في Aspose.Words؟

 ج: للتحقق من الخط الافتراضي المحدد في Aspose.Words ، يمكنك استخدام`DefaultFontName`ممتلكات`PdfOptions` class واسترداد اسم الخط الذي تم تكوينه.

#### س: هل من الممكن تحديد خط افتراضي مختلف لكل قسم من المستند؟

ج: نعم ، من الممكن تحديد خط افتراضي مختلف لكل قسم من المستند باستخدام خيارات التنسيق الخاصة بكل قسم. ومع ذلك ، قد يتطلب هذا معالجة أكثر تقدمًا للمستند باستخدام ميزات Aspose.Words.