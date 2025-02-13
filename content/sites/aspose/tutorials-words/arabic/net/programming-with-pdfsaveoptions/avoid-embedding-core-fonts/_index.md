---
title: تقليل حجم ملف PDF من خلال عدم تضمين الخطوط الأساسية
linktitle: تقليل حجم ملف PDF من خلال عدم تضمين الخطوط الأساسية
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تقليل حجم ملف PDF من خلال عدم تضمين الخطوط الأساسية عند تحويل مستندات Word إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

في هذا البرنامج التعليمي ، سنرشدك عبر خطوات كيفية تقليل حجم ملف PDF من خلال عدم تضمين الخطوط الأساسية مع Aspose.Words for .NET. تتيح لك هذه الميزة التحكم في ما إذا كان يجب تضمين الخطوط الأساسية مثل Arial و Times New Roman وما إلى ذلك في ملف PDF عند تحويل مستند Word. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند

ابدأ بتحميل مستند Word الذي تريد تحويله إلى PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

تأكد من تحديد المسار الصحيح لمستند Word الخاص بك.

## الخطوة 2: تعيين خيارات تحويل PDF

قم بإنشاء مثيل لفئة PdfSaveOptions وقم بتمكين تجنب تضمين الخط الأساسي:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

يتحكم هذا الخيار فيما إذا كان يجب تضمين الخطوط الأساسية في ملف PDF أم لا.

## الخطوة 3: تحويل المستند إلى PDF

 استخدم ال`Save` طريقة لتحويل مستند Word إلى PDF عن طريق تحديد خيارات التحويل:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

تأكد من تحديد المسار الصحيح لحفظ ملف PDF المحول.

### مثال على شفرة المصدر لتجنب تضمين الخطوط الأساسية باستخدام Aspose.Words for .NET

إليك الكود المصدري الكامل لاستخدام الميزة لتجنب تضمين الخط الأساسي مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// لن يتم تضمين ملف PDF الناتج مع الخطوط الأساسية مثل Arial و Times New Roman وما إلى ذلك.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

باتباع هذه الخطوات ، يمكنك التحكم بسهولة فيما إذا كان يجب تضمين الخطوط الأساسية في ملف PDF عند تحويل مستند Word باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية تقليل حجم ملف PDF من خلال عدم تضمين الخطوط الأساسية مع Aspose.Words for .NET. تتيح لك هذه الميزة التحكم في ما إذا كان يجب تضمين الخطوط الأساسية في ملف PDF عند تحويل مستند Word. باتباع الخطوات الموضحة ، يمكنك التحكم بسهولة في تضمين الخطوط الأساسية أو عدم دمجها ، مما يساعد في تقليل حجم ملف PDF وضمان توافق أفضل ومظهر متناسق للمستند على الأجهزة والأنظمة الأساسية المختلفة. لا تنسَ التفكير في عواقب عدم تضمين الخطوط الأساسية والتجربة للتأكد من أن المستند يتم عرضه كما هو متوقع.

### أسئلة مكررة

#### س: ما هو خيار عدم تضمين الخطوط الأساسية في ملف PDF ولماذا هو مهم؟
ج: يتحكم خيار عدم دمج الخطوط الأساسية في ملف PDF في ما إذا كان يجب تضمين الخطوط الأساسية مثل Arial و Times New Roman وما إلى ذلك في ملف PDF عند تحويل مستند Word. قد يكون هذا مهمًا لتقليل حجم ملف PDF عن طريق تجنب تضمين الخطوط المتاحة بشكل شائع في أنظمة قارئ PDF. يمكن أن يساعد أيضًا في ضمان توافق أفضل ومظهر متسق لمستند PDF عبر الأجهزة والأنظمة الأساسية المختلفة.

#### س: كيف يمكنني تكوين Aspose.Words for .NET لعدم تضمين الخطوط الأساسية في ملف PDF؟
ج: لتكوين Aspose.Words for .NET بحيث لا تقوم بتضمين الخطوط الأساسية في ملف PDF ، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد المستندات الخاصة بك عن طريق الاستبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي لدليل المستندات الخاص بك.

 قم بتحميل مستند Word الذي تريد تحويله إلى PDF باستخدام ملف`Document` فئة ومسار المستند المحدد.

 قم بإنشاء مثيل لـ`PdfSaveOptions`فئة وضبط`UseCoreFonts` ملكية ل`true`. سيؤدي ذلك إلى تجنب دمج الخطوط الأساسية في ملف PDF الذي تم إنشاؤه.

 استخدم ال`Save` طريقة`Document` لحفظ المستند بتنسيق PDF مع تحديد خيارات التحويل التي تم تكوينها مسبقًا.

#### س: ما هي فوائد عدم تضمين الخطوط الأساسية في ملف PDF؟
ج: فوائد عدم تضمين الخطوط الأساسية في ملف PDF هي:

تقليل حجم ملف PDF: من خلال تجنب تضمين الخطوط المتاحة بشكل شائع مثل Arial و Times New Roman وما إلى ذلك ، يمكن تقليل حجم ملف PDF ، مما يسهل تخزين الملفات ومشاركتها ونقلها.

توافق أفضل: باستخدام الخطوط الأساسية المتوفرة بشكل شائع في أنظمة قارئ PDF ، فإنك تضمن توافقًا أفضل ومظهرًا أفضل للمستند على الأجهزة والأنظمة الأساسية المختلفة.

#### س: ما هي النتائج المترتبة على عدم تضمين الخطوط الأساسية في ملف PDF؟
ج: النتائج المترتبة على عدم تضمين الخطوط الأساسية في ملف PDF هي كما يلي:

مظهر مختلف: إذا كانت الخطوط الأساسية غير متوفرة على النظام حيث يتم فتح PDF ، فسيتم استخدام الخطوط البديلة ، مما قد ينتج عنه مظهر مختلف عن المقصود.

مشاكل قابلية القراءة: قد لا تكون الخطوط البديلة المستخدمة مقروءة مثل الخطوط الأصلية ، مما قد يؤثر على سهولة قراءة المستند.