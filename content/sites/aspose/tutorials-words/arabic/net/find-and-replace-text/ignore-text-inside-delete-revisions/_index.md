---
title: تجاهل النص داخل حذف المراجعات
linktitle: تجاهل النص داخل حذف المراجعات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استخدام ميزة "تجاهل النص داخل حذف المراجعات" في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام ميزة "تجاهل النص داخل حذف المراجعات" في مكتبة Aspose.Words for .NET. هذه الميزة مفيدة عندما نريد تجاهل النص داخل مراجعات الحذف عند معالجة الكلمات مع المستندات.

## نظرة عامة على مكتبة Aspose.Words for .NET

قبل الخوض في تفاصيل الكود ، دعني أقدم باختصار مكتبة Aspose.Words for .NET. إنها مكتبة قوية تسمح بإنشاء وتعديل وتحويل مستندات Word في تطبيقات .NET. يوفر العديد من الميزات المتقدمة لمعالجة الكلمات مع المستندات ، بما في ذلك إدارة المراجعة.

## فهم ميزة "تجاهل النص داخل حذف المراجعات"

تتيح لك ميزة "تجاهل النص الداخلي حذف المراجعات" في Aspose.Words for .NET تحديد ما إذا كان يجب تجاهل النص الموجود داخل مراجعات الحذف أثناء عمليات معينة ، مثل البحث عن النص واستبداله. عند تمكين هذه الميزة ، لا يتم اعتبار النص المحذوف داخل المراجعات أثناء العمليات.

## الخطوة 1: إنشاء مستند جديد باستخدام Aspose.Words for .NET

 قبل أن نبدأ في معالجة النص في مستند ، نحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن أن يتم ذلك عن طريق إنشاء مثيل لملف`Document` هدف:

```csharp
Document doc = new Document();
```

## الخطوة 2: إدخال نص غير منقح في المستند

 بمجرد أن نحصل على مستند ، يمكننا إدراج نص لم تتم مراجعته باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال ، لإدراج النص "النص المحذوف" ، يمكننا استخدام الامتداد`Writeln` و`Write` طُرق:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## الخطوة 3: إزالة فقرة مع تتبع المراجعات

لتوضيح استخدام ميزة "تجاهل النص داخل حذف المراجعات" ، سنحذف فقرة من المستند باستخدام تتبع المراجعة. سيسمح لنا ذلك بمعرفة كيف تؤثر هذه الميزة على العمليات اللاحقة.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## الخطوة 4: تطبيق ميزة "تجاهل النص داخل حذف المراجعات"

 الآن وقد أعددنا وثيقتنا عن طريق حذف فقرة ، يمكننا تمكين ميزة "تجاهل النص داخل حذف المراجعات" باستخدام`FindReplaceOptions` هدف. سنقوم بتعيين`IgnoreDeleted` ملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## الخطوة 5: استخدام التعبيرات النمطية للبحث والاستبدال

لإجراء عمليات البحث والاستبدال على نص المستند ، سنستخدم التعبيرات العادية. في مثالنا ، سنبحث عن جميع تكرارات الحرف "e" ونستبدلها بعلامة النجمة "* ". .شبكة`Regex` يتم استخدام فئة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## الخطوة 6: عرض مخرجات الوثيقة المعدلة

بعد تطبيق البحث والاستبدال ، يمكننا عرض المحتوى الذي تم تغييره في المستند باستخدام`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

## الخطوة 7: تعديل الخيارات لتضمين النص المحذوف

 إذا أردنا تضمين نص محذوف في نتيجة الإخراج ، فيمكننا تغيير الخيارات لعدم تجاهل النص المحذوف. لهذا سنقوم بتعيين`IgnoreDeleted` ملكية ل`false`:

```csharp
options. IgnoreDeleted = false;
```

## الخطوة 8: إخراج المستند المعدل بالنص المحذوف

بعد تغيير الخيارات ، يمكننا إجراء البحث والاستبدال مرة أخرى للحصول على النتيجة مع تضمين النص المحذوف:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### مثال على شفرة المصدر لـ Ignore Text Inside Delete Revisions باستخدام Aspose.Words for .NET

إليك نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام ميزة "تجاهل النص داخل حذف المراجعات" مع Aspose.Words for .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// أدخل نصًا غير منقح.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// إزالة الفقرة الأولى مع تتبع المراجعات.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## خاتمة

في هذه المقالة ، استكشفنا شفرة المصدر C # لفهم كيفية استخدام ميزة "تجاهل النص داخل حذف المراجعات" في Aspose.Words for .NET. هذه الميزة مفيدة لتجاهل النص داخل مراجعات الحذف عند معالجة المستندات. اتبعنا دليلًا تفصيليًا لإنشاء مستند وإدراج نص وحذف فقرة مع تتبع المراجعة وتطبيق ميزة "تجاهل النص داخل حذف المراجعات" وإجراء عمليات البحث والاستبدال.

### التعليمات

#### س: ما هي وظيفة "تجاهل النص داخل حذف المراجعات" في Aspose.Words for .NET؟

ج: وظيفة "تجاهل النص الداخلي حذف المراجعات" في Aspose.Words for .NET تسمح لك بتحديد ما إذا كان يجب تجاهل النص الموجود داخل تنقيحات الحذف أثناء عمليات معينة ، مثل البحث عن النص واستبداله. عند تمكين هذه الميزة ، لا يتم اعتبار النص المحذوف داخل المراجعات أثناء العمليات.

#### س: ما المقصود بـ Aspose.Words لـ .NET؟

ج: Aspose.Words for .NET مكتبة قوية لإنشاء وتحرير وتحويل مستندات Word إلى تطبيقات .NET. يوفر العديد من الميزات المتقدمة لمعالجة الكلمات مع المستندات ، بما في ذلك إدارة المراجعة.

#### س: كيف يمكن إنشاء مستند جديد في Aspose.Words for .NET؟

 ج: قبل البدء في معالجة النص في مستند ما ، تحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words for .NET. يمكن القيام بذلك عن طريق إنشاء مثيل لملف`Document` هدف. فيما يلي نموذج التعليمات البرمجية لإنشاء مستند جديد:

```csharp
Document doc = new Document();
```

#### س: كيف يمكن إدراج نص غير محرّر في مستند باستخدام Aspose.Words for .NET؟

 ج: بمجرد حصولك على مستند ، يمكنك إدراج نص لم تتم مراجعته باستخدام ملف`DocumentBuilder` هدف. على سبيل المثال ، لإدراج النص "النص المحذوف" ، يمكنك استخدام الامتداد`Writeln` و`Write` طُرق:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### س: كيف يمكنني حذف فقرة مع تتبع المراجعة في Aspose.Words for .NET؟

ج: لتوضيح استخدام وظيفة "تجاهل النص داخل حذف المراجعات" ، سنقوم بحذف فقرة من المستند باستخدام تتبع المراجعة. سيسمح لنا ذلك بمعرفة كيف تؤثر هذه الوظيفة على العمليات اللاحقة.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### س: كيف يمكن تمكين ميزة "تجاهل النص الداخلي حذف المراجعات" في Aspose.Words for .NET؟

 ج: الآن بعد أن أعددنا وثيقتنا عن طريق حذف فقرة ، يمكننا تمكين ميزة "تجاهل النص داخل حذف المراجعات" باستخدام`FindReplaceOptions` هدف. سنقوم بتعيين`IgnoreDeleted` ملكية ل`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### س: كيف يتم البحث والاستبدال باستخدام التعبيرات النمطية في Aspose.Words for .NET؟

ج: لإجراء عمليات البحث والاستبدال على نص المستند ، سنستخدم التعبيرات العادية. في مثالنا ، سنبحث عن جميع تكرارات الحرف "e" ونستبدلها بعلامة النجمة "* ". سوف نستخدم .NET`Regex` فئة لهذا:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### س: كيف يتم عرض محتوى المستند الذي تم تغييره في Aspose.Words for .NET؟

ج: بعد تطبيق البحث والاستبدال ، يمكننا عرض المحتوى الذي تم تغييره في المستند باستخدام`GetText` طريقة:

```csharp
Console.WriteLine(doc.GetText());
```

#### س: كيف يتم تضمين نص محذوف في نتيجة الإخراج في Aspose.Words for .NET؟

 ج: إذا أردنا تضمين نص محذوف في نتيجة الإخراج ، فيمكننا تغيير الخيارات لعدم تجاهل النص المحذوف. لهذا ، سنقوم بتعيين`IgnoreDeleted` ملكية ل`false`:

```csharp
options. IgnoreDeleted = false;
```

#### س: كيف تظهر المستند المحرر مع النص المحذوف في Aspose.Words for .NET؟

ج: بعد تغيير الخيارات ، يمكننا إجراء بحث جديد واستبدال للحصول على النتيجة مع تضمين النص المحذوف:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
