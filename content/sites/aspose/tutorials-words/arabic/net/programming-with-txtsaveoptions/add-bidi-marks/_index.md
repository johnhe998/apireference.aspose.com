---
title: أضف علامات ثنائية الاتجاه في مستند Word
linktitle: أضف علامات ثنائية الاتجاه في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعلم كيفية إضافة علامات ثنائية الاتجاه إلى مستند Word باستخدام Aspose.Words for .NET وإنشاء مستندات احترافية متعددة اللغات.
type: docs
weight: 10
url: /ar/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الميزات التي تقدمها Aspose.Words القدرة على إضافة علامات ثنائية الاتجاه (ثنائية الاتجاه) إلى المستند. في هذا الدليل ، سنرشدك إلى كيفية استخدام الكود المصدري C # الخاص بـ Aspose.Words for .NET لإضافة علامات ثنائية الاتجاه إلى مستند.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل معالجة الكلمات بمستندات Word سهلة وفعالة. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها ، بما في ذلك إضافة علامات ثنائية الاتجاه.

## إنشاء الوثيقة وإضافة المحتوى

تتمثل الخطوة الأولى في إنشاء مستند جديد وإضافة محتوى إليه. استخدم فئة المستند لإنشاء مثيل مستند جديد. ثم استخدم فئة DocumentBuilder لإضافة نص إلى المستند. هنا مثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

في هذا المثال ، نقوم بإنشاء مستند جديد واستخدام DocumentBuilder لإضافة نص. لقد أضفنا ثلاثة أسطر نصية: واحد بالإنجليزية والآخر بالعبرية والآخر بالعربية لإثبات إضافة محتوى بلغات مختلفة.

## العلامات ثنائية الاتجاه المضافة

بمجرد إضافة المحتوى ، يمكننا الآن إضافة علامات ثنائية الاتجاه إلى المستند. لهذا ، نستخدم فئة TxtSaveOptions وقمنا بتعيين الخاصية AddBidiMarks على true. إليك الطريقة:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

في هذا المثال ، قمنا بإنشاء مثيل لـ TxtSaveOptions وقمنا بتعيين الخاصية AddBidiMarks على true. بعد ذلك ، نستخدم طريقة Save لفئة Document لحفظ المستند بعلامات ثنائية الاتجاه.

### مثال على شفرة المصدر لوظيفة "Add Bidi Marks" مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وإضافة محتوى
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// أضف علامات ثنائية الاتجاه
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## خاتمة

في هذا الدليل ، أوضحنا كيفية استخدام Aspose.Words for .NET لإضافة علامات ثنائية الاتجاه إلى مستند Word باستخدام كود المصدر C # المقدم. باتباع الخطوات المقدمة ، يمكنك بسهولة إضافة علامات ثنائية الاتجاه إلى مستندات Word في تطبيق C # الخاص بك. يوفر Aspose.Words مرونة وقوة هائلة لمعالجة الكلمات من خلال تنسيق النص وإدارة اللغة ، مما يسمح لك بإنشاء مستندات متعددة اللغات بشكل احترافي.

### أسئلة مكررة

#### س: ما المقصود بـ Aspose.Words لـ .NET؟
Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. يوفر العديد من الميزات لمعالجة الكلمات باستخدام مستندات Word ، بما في ذلك إضافة علامات ثنائية الاتجاه (ثنائية الاتجاه).

#### س: ما هي الميزات التي تقدمها Aspose.Words for .NET؟
تقدم Aspose.Words for .NET مجموعة كبيرة من الميزات لإنشاء مستندات Word وتعديلها ومعالجتها. تتضمن بعض هذه الميزات إنشاء المستندات وإضافة المحتوى وتنسيق النص وإدارة الجداول ودمج المستندات وتقسيمها وتحويل المستندات والمزيد.

#### س: كيف يمكنني إضافة علامات ثنائية الاتجاه إلى مستند Word باستخدام Aspose.Words for .NET؟
يمكنك إضافة علامات ثنائية الاتجاه إلى مستند Word باتباع الخطوات التالية:

 قم بإنشاء مستند جديد باستخدام امتداد`Document` فصل.

 استخدم ال`DocumentBuilder` فئة لإضافة محتوى إلى المستند.

 بمجرد إضافة المحتوى ، استخدم`TxtSaveOptions`فئة وضبط`AddBidiMarks` ملكية ل`true`.

 احفظ المستند بعلامات ثنائية الاتجاه باستخدام ملف`Save` طريقة`Document` فصل.

#### س: هل تدعم Aspose.Words لغات متعددة لإضافة علامات ثنائية الاتجاه؟
نعم ، يدعم Aspose.Words لغات متعددة لإضافة علامات ثنائية الاتجاه. يمكنك إضافة علامات ثنائية الاتجاه إلى نص بلغات مختلفة ، مثل الإنجليزية والعبرية والعربية ، باستخدام Aspose.Words for .NET.

#### س: هل هناك أي خيارات إضافية لحفظ المستند بعلامات ثنائية الاتجاه؟
 نعم ، يمكنك تحديد خيارات أخرى عند حفظ المستند بعلامات ثنائية الاتجاه باستخدام امتداد`TxtSaveOptions` فصل. على سبيل المثال ، يمكنك ضبط تنسيق حفظ المستند وخيارات الترميز وما إلى ذلك.