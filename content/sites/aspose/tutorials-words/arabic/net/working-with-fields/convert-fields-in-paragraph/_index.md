---
title: تحويل الحقول في الفقرة
linktitle: تحويل الحقول في الفقرة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تحويل حقول IF إلى نص عادي في فقرة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/convert-fields-in-paragraph/
---

إليك برنامج تعليمي يوضح كيفية استخدام ميزة تحويل الحقول إلى فقرة مع Aspose.Words for .NET. يحول هذا الرمز جميع حقول كتابة IF التي تمت مواجهتها في الفقرة الأخيرة من المستند إلى نص عادي. اتبع الخطوات أدناه لفهم وتشغيل هذا الرمز.

تأكد من تثبيت Aspose.Words for .NET وقم بإعداد بيئة التطوير الخاصة بك قبل أن تبدأ.

## الخطوة 1: استيراد المراجع

لاستخدام Aspose. Words في مشروعك ، تحتاج إلى إضافة المراجع الضرورية. تأكد من إضافة مرجع إلى مكتبة Aspose.Words في مشروعك.

## الخطوة الثانية: تحميل المستند

قبل أن تتمكن من تحويل الحقول ، يجب عليك تحميل المستند الذي يحتوي على الحقول المراد تحويلها. تأكد من تحديد المسار الصحيح للدليل الذي يحتوي على المستند. إليك كيفية تحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند.
Document doc = new Document(dataDir + "Linked fields.docx");
```

استبدل "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة 3: تحويل الحقول إلى نص

الآن بعد أن تم تحميل المستند ، يمكننا المضي قدمًا في تحويل حقول الكتابة إلى نص عادي. في هذا المثال ، نستهدف الحقول الموجودة في الفقرة الأخيرة من المستند فقط. هذا هو الكود الذي يقوم بهذا التحويل:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

يستخدم هذا الرمز مجموعة من أساليب LINQ لتصفية الحقول في الفقرة الأخيرة من المستند ثم تحويلها إلى نص عادي عن طريق استدعاء`Unlink()` طريقة.

## الخطوة 4: حفظ المستند المعدل

 بمجرد تحويل الحقول ، يمكنك حفظ المستند المعدل. استخدم ال`Save()` طريقة لذلك. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف للنسخ الاحتياطي.

### مثال على رمز المصدر لـ Convert Fields In Paragraph باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند.
Document doc = new Document(dataDir + "Linked fields.docx");

// تحويل حقول IF إلى نص عادي في الفقرة الأخيرة من المستند.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// احفظ المستند المعدل.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### التعليمات

#### س: ما هو حقل التحويل في Aspose.Words؟

ج: حقل التحويل في Aspose. تعتبر Words نوعًا من الحقول التي تحول قيمة أو تعبيرًا إلى تنسيق أو نوع بيانات آخر. على سبيل المثال ، يمكنك استخدام حقل تحويل لتحويل تاريخ إلى تنسيق معين ، أو رقم إلى نص ، أو إجراء أنواع تحويلات أخرى.

#### س: كيفية إدراج حقل تحويل في فقرة باستخدام Aspose.Words؟

ج: لإدراج حقل تحويل في فقرة باستخدام Aspose.Words ، يمكنك اتباع الخطوات التالية:

1. قم باستيراد فئة المستند من مساحة الاسم Aspose.Words.
2. قم بإنشاء مثيل من المستند عن طريق تحميل المستند الحالي.
3. احصل على الفقرة حيث تريد إدراج حقل التحويل.
4. استخدم أسلوب InsertField لإدراج حقل التحويل بالصيغة الصحيحة.

#### س: ما هي تنسيقات التحويل التي يدعمها Aspose.Words؟

ج: Aspose.Words تدعم مجموعة واسعة من تنسيقات التحويل في الحقول ، بما في ذلك تنسيقات التاريخ وتنسيقات الأرقام وتنسيقات النص وتنسيقات العملات وتنسيقات النسبة المئوية والمزيد. يمكنك التحقق من وثائق Aspose.Words للحصول على قائمة كاملة بصيغ التحويل المتاحة.

#### س: كيف يتم تحديث حقل التحويل في مستند Word باستخدام Aspose.Words؟

ج: لتحديث حقل التحويل في مستند Word باستخدام Aspose.Words ، يمكنك استخدام طريقة UpdateFields. تتنقل هذه الطريقة عبر المستند وتقوم بتحديث جميع الحقول ، بما في ذلك حقول التحويل ، وإعادة حساب القيم بناءً على البيانات الحالية.