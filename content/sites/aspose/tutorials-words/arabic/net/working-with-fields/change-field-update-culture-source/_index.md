---
title: تغيير مصدر ثقافة تحديث الحقل
linktitle: تغيير مصدر ثقافة تحديث الحقل
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تغيير مصدر ثقافة تحديث الحقل ، دليل خطوة بخطوة لتعديل مصدر الثقافة في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/change-field-update-culture-source/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تغيير مصدر ثقافة التحديث الميداني في مستندات Word باستخدام Aspose.Words for .NET. من خلال تعديل مصدر الثقافة ، يمكنك التحكم في تنسيق التاريخ أثناء تحديث الحقل وعمليات دمج البريد. سنزودك بشفرة المصدر C # الضرورية والتعليمات خطوة بخطوة لتحقيق ذلك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند و DocumentBuilder
للبدء ، قم بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل محتوى بلغة محددة
بعد ذلك ، قم بتعيين الإعدادات المحلية على اللغة الألمانية وأدخل الحقول بتنسيق التاريخ:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

في الكود أعلاه ، قمنا بتعيين لغة الخط إلى الألمانية (معرف اللغة 1031) وقمنا بإدخال حقلين بتنسيق تاريخ محدد.

## الخطوة 3: تغيير مصدر ثقافة تحديث الحقل
لتغيير مصدر ثقافة تحديث الحقل ، استخدم فئة FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

في هذا المثال ، قمنا بتعيين الثقافة المستخدمة أثناء التحديث الميداني ليتم اختيارها من الثقافة المستخدمة في الحقل.

## الخطوة 4: قم بإجراء دمج المراسلات
نفذ عملية دمج المراسلات وحدد قيمة التاريخ للحقل "Date2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

في مقتطف الشفرة هذا ، نقوم بتنفيذ عملية دمج البريد وتوفير قيمة DateTime للحقل "Date2".

## الخطوة 5: احفظ المستند
احفظ المستند المعدل في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### مثال رمز المصدر لتغيير مصدر ثقافة تحديث الحقل باستخدام Aspose.Words for .NET
فيما يلي رمز المصدر الكامل لتغيير مصدر ثقافة تحديث الحقل في مستندات Word باستخدام Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تغيير مصدر ثقافة التحديث الميداني في مستندات Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن التحكم في الثقافة المستخدمة لتنسيق التاريخ أثناء عمليات تحديث الحقل ودمج البريد. قم بتخصيص مصدر الثقافة وفقًا لمتطلباتك لضمان تاريخ دقيق ومتسق.

### التعليمات

#### س: كيف يمكنني تغيير مصدر ثقافة التحديث الميداني في Aspose.Words for .NET؟

 ج: لتغيير مصدر ثقافة التحديث الميداني في Aspose.Words for .NET ، يمكنك استخدام`Document.FieldOptions.CultureSource` الممتلكات وقيمتها على`FieldCultureSource.FieldCode` أو`FieldCultureSource.CurrentThread` . على سبيل المثال ، يمكنك استخدام ملفات`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` لاستخدام الثقافة المحددة في رمز الحقل.

#### س: كيف يمكنني تحديد ثقافة معينة لتحديث الحقول في Aspose.Words for .NET؟

ج: لتحديد ثقافة معينة لتحديث الحقول في Aspose.Words for .NET ، يمكنك استخدام`Document.FieldOptions.FieldUpdateCultureInfo` الممتلكات وتعيين`CultureInfo` الكائن المطابق للثقافة المرغوبة. على سبيل المثال ، يمكنك استخدام ملفات`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` لتحديد الثقافة الفرنسية (الفرنسية).

#### س: هل من الممكن تعطيل التحديث التلقائي للمجال في Aspose.Words for .NET؟

 ج: نعم ، من الممكن تعطيل التحديث التلقائي للحقل في Aspose.Words for .NET. يمكنك استخدام ال`Document.FieldOptions.UpdateFields` الملكية وضبطها على`false` لمنع الحقول من التحديث التلقائي. يتيح لك هذا التحكم يدويًا في تحديث الحقول حسب الحاجة.

#### س: كيف يمكنني تحديث حقول المستند يدويًا في Aspose.Words for .NET؟

 ج: لتحديث الحقول في مستند يدويًا في Aspose.Words for .NET ، يمكنك استخدام`Field.Update` طريقة لكل مجال على حدة. على سبيل المثال ، يمكنك استخدام ملفات`field.Update()` لتحديث المجال المحدد.